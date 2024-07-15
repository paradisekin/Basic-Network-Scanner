# Basic-Network-Scanner

Port Scanner Tool
Overview
This Python-based script is designed to scan a range of ports (50-85) on a specified hostname to identify open ports. It translates hostnames to IPv4 addresses using socket.gethostbyname() and employs socket connections with a timeout of 1 second per port. This tool is useful for enhancing network security and management by quickly identifying open ports.

Features
Scans a specific range of ports (50-85)
Translates hostnames to IPv4 addresses
Identifies open ports within the specified range
Uses socket connections with a 1-second timeout per port
Prints a list of open ports for easy identification


Here is the code :


#!/bin/python3

import sys
import socket
from datetime import datetime

# Define our Target
if len(sys.argv) == 2:
    target = socket.gethostbyname(sys.argv[1])  # translate the hostname to ipv4
else:
    print("Invalid amount of arguments.")
    print("Syntax: Python3 scanner.py <ip>")
    sys.exit()

# Add a pretty banner
print("-" * 50)
print("Scanning target: " + target)
print("Time Started: " + str(datetime.now()))
print("-" * 50)

try:
    for port in range(50, 85):
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)  # here AF_INET is the IP
        s.settimeout(1)  # this will scan a port for 1 sec
        result = s.connect_ex((target, port))
        if result == 0:
            print(f"Port {port} is open")
        s.close()

except KeyboardInterrupt:
    print("\nExiting program.")
    sys.exit()

except socket.gaierror:
    print("Hostname could not be resolved.")
    sys.exit()

except socket.error:
    print("Could not connect to server.")
    sys.exit()


