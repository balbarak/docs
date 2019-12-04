# Share Folder from Ubuntu to Windows

Setup folder to share it with Windows

## Install Samba

`sudo apt-get install samba`

`sudo apt-get install samba-common`

## Create dir to share

`sudo mkdir /home/share`

## Set dir permisson to allow anyonmouse

`sudo chmod 0777 /home/share`

`sudo chown -R nobody:nogroup /home/share`

## Edit sambe config

`sudo nano /etc/samba/smb.conf`

### Replace with

```js
[globa]
workgroup = WORKGROUP
server string = Samba Server %v
netbios name = ubuntu
security = user
map to guest = bad user
name resolve order = bcast host
dns proxy = no
bind interfaces only = yes

# == Share Folder===
# Folder Name Public
[Public]
path = /home/Public
writable = yes
guest ok = yes
guest only = yes
read only = no
create mode = 0777
directory mode = 0777
force user = nobody

#Protect Folder Name Prot (name as its appear in Windows)
[Prot]
path = /home/protected
read only = no
wrtiable = yes
browsable = yes
valid users = <user>
create mask = 0640
directory mask = 750
```
## Restart Samba service

`sudo systemctl restart smbd`
