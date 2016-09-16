Fast Local IP Discover
======================

Fast Local IP Discover or Flip, tries to find as quickly as possible every
hardware on a local network.

It outputs IPs, MACs and Vendors. For example:

    d0:87:e2:__:__:__ 192.168.0.12 Samsung Electronics Co.,Ltd
    00:25:5c:__:__:__ 192.168.0.10 NEC Corporation
    34:af:2c:__:__:__ 192.168.0.11 Nintendo Co., Ltd.
    00:07:cb:__:__:__ 192.168.0.254 FREEBOX SAS

Flip uses the GNU parallel utility to massively run parallel pings which, in
turns, will fill the ARP cache table. This table is then parsed to look for
hardware.

The MAC prefixes are compared to a static list of vendor prefixes.

Requirements
------------

Flip requires:

- parallel
- an access to /proc/net/arp

On Debian, `parallel` can be installed with `sudo apt-get install parallel`.

Notes
-----

Flip only looks for local IP addresses like 192.168.0.*

