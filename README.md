# How to install next cloud on Ubuntu 20.04 LTS

Add A record on domain DNS record by pointing IP address

Open your terminal or cmd

```ssh root@ip-address
```

Add a new user

adduser username

Example: adduser aadhil

Add User to sudo group as have sudo privilege.

usermod -aG sudo username
Example: usermod -aG sudo aadhil 

Change the user 

su username
Example: su aadhil

cd ..

Check firewall is active or not to do so
sudo ufw status

To check what apps are in the list
sudo ufw app list

Make sure OpenSSH is allowed to do so:
sudo ufw allow OpenSSH

Above command will update rules

Now lets enable ufw (below command will make firewall active):
sudo ufw enable
sudo ufw status

Next we need to unable port 80 and port 443 

sudo ufw allow 80,443/tcp
sudo ufw status

Install snap (Snap is a software packaging and deployment system developed by Canonical for the operating systems that use the Linux kernel.)
https://snapcraft.io/docs/installing-snap-on-ubuntu
$ sudo apt update
$ sudo apt install snapd

We need to get nextcloud installation now using snap:
$ sudo snap install nextcloud

The above command will install NEXTCLOUD on server completely. Now you will be able to access the the nextcloud using browser (by IP or ifdomain is already connected then by domain)


Now lets enable lets-encrypt (SSL certificate)
sudo nextcloud.enable-https lets-encrypt

