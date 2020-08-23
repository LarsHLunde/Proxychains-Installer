# Proxychains Installer
This is a script for installing a compiled version of ProxyChains ver. 4.2.0 by haad on RHEL7/OEL7
May work on other OS's, I have no real reason to test.

I don't know how kosher this is,
but all I've done is compile the proxychains project by haad:   
https://github.com/haad/proxychains

tar.gziped it, put it in base64, put it in a bash file,
and place them on the system for use.

It may be an interesting exercise in bash scripting for some,
but it's just for basic deployment when reverse-proxying servers for my own use.

To use, download install.sh and run or
```
curl -O https://raw.githubusercontent.com/LarsHLunde/Proxychains-Installer/master/install.sh
sudo bash install.sh
```

How project was generated on OEL7:
```
sudo yum groupinstall "development tools" -y
git clone https://github.com/haad/proxychains.git
cd proxychains
make
tar cfzv proxy.tar.gz libproxychains4.so proxychains4
base64 proxy.tar.gz > out.base64
```
