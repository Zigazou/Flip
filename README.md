Fast Local IP Discover
======================

Fast Local IP Discover or Flip, tries to find as quickly as possible every
hardware on a local network.

It outputs IPs, MACs and Vendors. For example:

    192.168.0.12 d0:87:e2:__:__:__ "Samsung Electronics Co.,Ltd"
    192.168.0.10 00:25:5c:__:__:__ "NEC Corporation"
    192.168.0.254 00:07:cb:__:__:__ "FREEBOX SAS"

Flip uses the GNU parallel utility to massively run parallel pings which, in
turns, will fill the ARP cache table. This table is then parsed to look for
hardware. The MAC addresses are then looked for using the `macvendors.co` API.

Requirements
------------

Flip requires:

- parallel
- curl
- arp command located in /usr/sbin

On Debian, these can be installed with `sudo apt-get install parallel curl`.

Notes
-----

Flip only looks for local IP addresses like 192.168.0.*

