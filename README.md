# Checkpoint VPN cookbook

This tutorial is based on a post from [professor coruja]

## Basic Install

First of all, make sure you have these packages installed:

* libstdc++5 (32 bits):
* libpam0g

You can run these commands to check if the packages are already installed.

``` bash
sudo apt list --installed|grep libstdc++5.*386
sudo apt list --installed|grep libpam0g.*386
```

If something is missing, install with:

``` bash
dpkg –add-architecture i386
apt-get update
apt-get install libstdc++5:i386 libpam0g:i386
```

Next, run the bash script *snx_install.sh*

``` bash
bash snx_install.sh
```

## Examples of use

The command below connect to a network *vpn.company_domain.com* with username *your_username* and prompts for a password:

``` bash
snx -g -s vpn.company_domain.com -u your_username
```

If you wish to connect automaticaly to the network without prompt for a password you can store this line in your .profile:

``` bash
echo "your_password" | snx -g -s vpn.company_domain.com -u your_username <&0
```

> Don't forget to check the version of snx after connect:

```
Check Point's Linux SNX
build 800007075
```


[professor coruja]: http://blog.professorcoruja.com/2010/11/como-instalar-vpn-checkpoint-no-linux.html
