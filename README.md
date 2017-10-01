# switchking-docker

# lsusb
Bus 002 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 004 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 003 Device 002: ID 1781:0c31 Multiple Vendors Telldus TellStick Duo
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub




lsusb -D /dev/bus/usb/003/002 | grep -F "Device:"




--build-arg <varname>=<value>
