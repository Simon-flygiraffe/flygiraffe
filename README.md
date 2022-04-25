Created on Fri Jul  2 18:17:18 2021
@author: sgolan

# Hi User !  This script is performs the following:

- receives a list of linux servers, ssh to each one & retrieves a system info from each one of them and aggregates in one reporting file:
- Informatoin which will be retrieved: hostname;os & kernel detais system;Time & ntp state;num of CPUs;CPU models;NICs installed and status;num of nvme devices
- before running, make sure you have paramiko and argparse modules installed (pip3 install paramiko argparse)
- For running it, you'll have to provide a path to a hosts file, and the password for the root user. 
- Proper way of running this script:

#### `python3 system_info_light.py 'hosts_path.txt' 'admin'` 

Sample output file:

```
SYSTEM INFO FOR HOST:    ---->>>     rack02-server83

OS & KERNEL DETAILS:
            Kernel: Linux 4.14.252-001730324769e3ea3c709-rel-lb
  Operating System: CentOS Linux 7 (Core)
      Architecture: x86-64

ALL IP-V4 ADDRESSES:
    inet 192.168.18.200/20 brd 192.168.31.255 scope global noprefixroute eno1
    inet 172.16.231.155/24 brd 172.16.231.255 scope global noprefixroute enp59s0f1


SYSTEM TIME & NTP STATUS: 
Mon Apr 25 11:11:50 UTC 2022
synchronised to NTP server (178.63.9.212) at stratum 3
   time correct to within 123 ms
   polling server every 512 s
     NTP enabled: no


CPU MODEL:
model name	: Intel(R) Xeon(R) Gold 5218R CPU @ 2.10GHz


NUM OF CPU'S IN THE SERVER: 
80


LIST EXISTING NETWORK CARDS & WHICH NIC IS UP:
Bus info          Device     Class          Description
=======================================================
pci@0000:18:00.0  eno1       network        FastLinQ QL41000 Series 10/25/40/50GbE Controller
pci@0000:3b:00.1  enp59s0f1  network        Ethernet Controller E810-C for QSFP
2: eno1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP mode DEFAULT group default qlen 1000
5: enp59s0f1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP mode DEFAULT group default qlen 1000


TOTAL NUM OF NVME DEVICES:
16


***END OF REPORT FOR THIS HOST***  >  >  >  >  >  >  >  >  >  >  >  >  >  >  >  NEXT HOST...
```
