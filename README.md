# ansible

## Prepare ubuntu 21.04 VM

###  Download newest ubuntu version from https://ubuntu.com/#download

1. Insert ubuntu Live CD in Virtual CD-ROM of Virtualbox

###  Configuration for Virtualbox VM Network
- Bridget Adapter
- Name of host ethernet adapter
- Promiscuous Mode: Allow VMs
- Cable connected

###  Start VM

###  install open-ssh on VM
```
sudo apt-get install openssh-server
```

###  add new user as admin on VM
```
sudo adduser <userName>
sudo usermod -aG sudo <userName>
# verify user as admin
sudo - <userName>
```

###  add IP-Address to hostsfile on HOST
add IP-ADDRESS with <VM-Name>
```
vi /etc/hosts
```

###  Create .ssh directory if not exists
A better approach is the following command
```
ssh-copy-id <userName>@<VM-Name>
```
 which does all the following automatically

or manually

```
mdir ~/.ssh
chmod 700 ~/.ssh
```

###  copy ssh public key to new user home directory from HOST
```
sudo scp ~/.ssh/id_rsa.pub <userName>@<VM-Name>:.ssh/authorized_keys
# verify ssh connection
ssh <userName>@<VM-Name>
```



