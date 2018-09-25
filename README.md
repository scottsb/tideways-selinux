# SELinux Module for Tideways

Simple SELinux module for Tideways daemon. Hopefully will be obsolete once this feature is completed:

https://tideways.featureupvote.com/suggestions/17139/add-support-for-selinux-out-of-the-box

## Compatibility

This has only been tested on CentOS 7 (specifically 7.5). It likely mostly works with CentOS 6 as well, but it may require some light changes.

## How to Install

1. Make sure SELinux dev tools are installed on the server:

        sudo yum install -y selinux-policy-devel

2. Clone or [download](https://github.com/scottsb/tideways-selinux/archive/master.zip) this repository to the server.

3. From within the repository directory run these commands:

        make -f /usr/share/selinux/devel/Makefile tideways.pp
        sudo semodule -i tideways.pp
        sudo restorecon -F -R -v $(<tideways_paths)
