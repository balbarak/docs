# Ubuntu Network Interface Commands

* `ifconfig -a` to list all network interfaces in the system
* `route -n` to get a network route path

## Fireewall

To get status of the firewall
 > `sudo ufw status`

Turn off firewall 
> `sudo ufw disable` 

Turn on firewall
> `sudo ufw enable`  

Disable network interface
> `sudo ifconfig eth0 down` 

Enable network interface
> `sudo ifconfig eth0 up` 

## Set Static IP Address
Edit netplan config

> `sudo nano /etc/netplan/50-cloud-init.yaml` 

With

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

Apply netplan changes

> `sudo netplan apply` 
