# Ubuntu Network Interface Commands

* `ifconfig -a` to list all network interfaces in the system
* `route -n` to get a network route path

## Fireewall

* `sudo ufw status` to get status of the firewall
* `sudo ufw disable` turn off firewall
* `sudo ufw enable`  turn on firewall
* `sudo ifconfig eth0 down` disable network interface
* `sudo ifconfig eth0 up` enable network interface

## Set Static IP Address

* `sudo nano /etc/netplan/50-cloud-init.yaml` edit config

```Javascript
network:
 version: 2
  renderer: networkd
   ethernets:
   eth0:
    addresses: []
    dhcp4:true
    eth1:
     dhcp4: no
     addresses: [10.0.0.4/24]
     gateway4: 0.0.0.0
     nameservers:
       addresses: [8.8.8.8,8.8.4.4]

```

* `sudo netplan apply` to apply the changes
