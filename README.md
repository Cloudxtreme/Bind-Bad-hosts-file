# Bind Bad hosts file to block domains on a network
## About
A bad hosts file for Bind, to block out the bad on your network!

This is simply a maintained list of bad hosts in the format of bind, so that you can simply copy/paste it into your bind config and block out those unwanted domains from your network.

The original author of the host file:

http://hosts-file.net/?s=Download

They get all the credit. I simply combined, cleaned up, and made mass text edits to fit the format. 

## Instructions

* Setup a cheap ubuntu server from ubuntu.org
* Install bind, but typing: "sudo apt-get install bind9"
* Edit your /etc/named.conf with nano by typing "sudo nano /etc/bind/named.conf"
* Copy/Paste the contents of this file at the bottom
* Then create and edit your block dns file, by typing: "sudo nano /etc/bind/block" and putting the contents of the "block" file that's in the git.
* Make sure to edit server.yourdomain.com with your DNS server name and hostmaster.yourdomain.com with your email address.
* Restart bind with: "sudo service bind9 restart"
