ip-info
=======

ip-info is a simple software package for determining IP address information 
without using a video monitor. The IP address can be displayed as flashes 
on the system LED or read over the system speakers using espeak. 

This software lets you determine your system's IP address without an 
attached video monitor. It was designed for use with the Raspberry 
Pi computer, but may be used on many other types of systems.

This package provides two scripts and two services. The scripts are:

1. ip-read :: reads the IP address over the system's speakers

This script finds the first non-loopback IPv4 address and reads it aloud 
using espeak.

2. ip-flash :: flashes the IP address over the system LED

This script finds the first non-loopback IPv4 address and flashes it 
on the system LED (/sys/class/leds/led0 by default).

    1 - 9 short flashes indicate the digits 1 - 9
    10 short flashes indicate the digit 0
    a long flash indicates an octet separator (dot)
    a brief pause separates digits 

After ip-flash runs, the LED is reconnected to its original trigger 
(mmc, wireless, etc).


Each of these scripts has a corresponding systemd unit file and can be 
enabled to run on boot; these can be enabled with these commands:

    systemctl enable ip-read.service
    systemctl enable ip-flash.service 

This software is made available under the terms of the GNU General 
Public License, version 2.0, or (at your option) any later version.

Your feedback on these scripts is welcome; please contact the author at:

   Chris Tyler <chris@tylers.info>
   ctyler on irc://irc.freenode.net/seneca

This package is hosted on GitHub at https://github.com/ctyler/ip-info

