# Checkpoint VPN cookbook

This tutorial is based on a post from [professor coruja]

## Basic Install

First of all, make sure you have these packages installed:

- libstdc++5 (32 bits):
- libpam0g

You can run these commands to check if the packages are already installed.

```bash
sudo apt list --installed|grep libstdc++5.*386
sudo apt list --installed|grep libpam0g.*386
```

If something is missing, install with:

```bash
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libstdc++5:i386 libpam0g:i386
```

Next, run the bash script _snx_install.sh_

```bash
bash snx_install_7075.sh
```

## Troubleshooting

If snx command still fails to connect, try to install these libs:

```bash
sudo apt install lib32stdc++6 lib32z1 lib32readline7 lib32gcc1 libpam0g:i386 libstdc++5:i386 libx11-6:i386
```

sudo apt install lib32stdc++6 lib32z1 lib32readline7 lib32gcc1 libpam0g:i386 libstdc++5:i386 libx11-6:i386

## Examples of use

### Connect

The command below connect to a network _vpn.company_domain.com_ with username _your_username_ and prompts for a password:

```bash
snx -g -s vpn.company_domain.com -u your_username
```

If you wish to connect automaticaly to the network without prompt for a password you can store this line in your .profile:

```bash
echo "your_password" | snx -g -s vpn.company_domain.com -u your_username <&0
```

> Don't forget to check the version of snx after connect:

```
Check Point's Linux SNX
build 800007075
```

### Disconnect

```bash
snx -d
```

[professor coruja]: http://blog.professorcoruja.com/2010/11/como-instalar-vpn-checkpoint-no-linux.html
