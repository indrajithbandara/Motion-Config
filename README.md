Motion_config
=============

All fileslicensed by GPL version 2.0 or higer

Author - Eugene Lityushkin 2014

evgeny.lityushkin@gmail.com

Overview

In first, this project is example of motion installation and configuration for home video recording system.

I have old x86 Mageia Linux netbook and use it as vide recording device.
Capturing videfiles transmited to remoute motion host - virtual machine based on Mageia Linux in Virtualbox.


Mageia-host1 + motion (192.168.1.41)----> Nat (192.168.1.1 & real ip)---->Internet----> Nat(real ip and internal ip)----> Mageia-host2 + motion on VirtualBox 

This schema provede:

1. Capturing video on Mageia Linux Host 1 with embeded cam and usb web cam

2. Local storaging of capturing video 

3. Translation capturing video in home network (WiFi or Ethernet)

4. Transmitted captrueing vide over internet to remode Mageia host2 


Step 1.

Configure ssh keybased authentication on Mageia Host1 and Mageia Host2

Step 2. Edited inventory file ./mageia-hosts/inventory 

Step 3.  Use ansible command:

For install role Master (Mageia-host1):

ansible-playbook -vvv -i ./mageia-hosts/inventory master.yml --limit=master

For install role Slave (Mageia-host2):

ansible-playbook -vvv -i ./mageia-hosts/inventory slave.yml --limit=slave


Step4

Login into motion on Master node - enter http://<master-ip-address>:8081 in browser adress string


   



Old instruction see in Motion config HOWTO and Examples of motion and ssmtp config files.


