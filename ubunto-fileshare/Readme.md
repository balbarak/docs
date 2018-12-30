# Share Folder from Ubuntu to Windows

Setup folder to share it with Windows

## Install Samba

`sudo apt-get install samba`

`sudo apt-get install samba-common`

`sudo apt-get install python-glade2`

`sudo system-config-samba`

## Create dir to share

`sudo mkdir /home/share`

## Edit sambe config

`sudo nano /etc/samba/smb.conf`

### Replace with

```js
[globa]
worgroup = WORKGROUP
server string = Samba Server %v
netbios name = UBUNTU-SERVER
security = user
map to guest = bad user
name resolve order = bcast host
dns proxy = no
bind interfaces only = yes

# == Share Folder===
# Folder Name Public
[Public]
path = /home/share
wrtable = yes
quest ok = yes
quest only = yes
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

## Add sambe user
`sudo addgroup mygroup`

`sudo adduser user mygroup`

`sudo smbpasswd -a user`

## Change owner and permissions

`sudo chown -v -R root:mygroup /home/protected`

`sudo chmod -v -R 0770 /home/protected`