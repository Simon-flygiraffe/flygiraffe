Created on Fri Jul  2 18:17:18 2021
@author: sgolan
                                **Hi User** !  This script is performs the following:

- receives a list of linux servers, ssh to each one & retrieves a system info from each one of them and aggregates in one reporting file:
- Information which will be retrieved : | hostname | System Time | num of CPUs | CPU models | NIC installed | drives installed |
- For running it, you have to provide a file path where a hosts file is placed, and the hosts password. (script is ssh as root)
- before running, make sure you have paramiko and argparse modules installed
- Proper way of running this script: (assuming hosts file is in same location as the script)
- python system_info_light.py "hosts_file" "admin"
