# Configuring a SECOND Raspberry Pi WiFi interface as an Access Point

## USB Wifi Adapter install

The first step is to install the secondary WiFi adapter.

The command `lsusb` should show the device ([lsusb example output](lsusb.txt).

I used a "tp-link 300Mbps Mini Wireless N USB Adapter" TL-WN823N

(uses 8192eu driver)

Instructions &  Raspbian drivers at [fars-robotics.net](http://fars-robotics.net)

First step is work out which type of wifi chip is in your USB wifi adapter (by searching
the internet). Eg. in the UK tp-link TL-WN823N it is '8192eu'. Clicking the 
[Directory of available wifi drivers](http://downloads.fars-robotics.net/wifi-drivers/)
gives you a directory-per-driver.

Within the directory (e.g. 
[8192su](http://downloads.fars-robotics.net/wifi-drivers/8192su-drivers/) is the 
long list of available driver versions.

Type `uname -a` to get the version / build number required to select the right file.

Easy install:
```
sudo wget http://fars-robotics.net/install-wifi
sudo chmod +x install-wifi
sudo ./install-wifi
```

## dhcpcd.conf

`dhcpcd` is the DHCP *client* for the Raspberry Pi.

`/etc/dhcpcd.conf`
[example](dhcpcd.conf)

## hostapd

`sudo apt install hostapd`

`/etc/hostapd/hostapd.conf`
[example](hostapd.conf)

## dnsmasq

`sudo apt install dnsmasq`

`/etc/dnsmasq.conf`
[example](dnsmasq.conf)

