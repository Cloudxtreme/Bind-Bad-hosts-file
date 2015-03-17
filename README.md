# Bind Bad hosts file to block domains on a network
## About
A bad hosts file for Bind, to block out the bad on your network!

This is simply a maintained list of bad hosts in the format of bind, so that you can simply copy/paste it into your bind config and block out those unwanted domains from your network.

The original author of the hosts files that I combined and edited are here:

http://hosts-file.net/?s=Download
http://someonewhocares.org/hosts/

They get all the cedit. I simply combined, cleaned up, and made mass text edits to fit the format. 

## Instructions

* Setup a cheap ubuntu server from ubuntu.org
* Install bind, but typing: "sudo apt-get install bind9"
* Edit your /etc/named.conf with nano by typing "sudo nano /etc/bind/named.conf"
* Copy/Paste the contents of this file at the bottom
* Then create and edit your block dns file, by typing: "sudo nano /etc/bind/block" and putting these contents in it:
       $TTL 24h

   @       IN SOA server.yourdomain.com. hostmaster.yourdomain.com. (
                  2003052800  86400  300  604800  3600 )

   @       IN      NS   server.yourdomain.com.
   @       IN      A    127.0.0.1
   *       IN      A    127.0.0.1
   *       
   
* Restart bind with: "sudo service bind9 restart"
