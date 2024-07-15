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
