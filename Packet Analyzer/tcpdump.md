## Scenario
You’re a network analyst who needs to use tcpdump to capture and analyze live network traffic from a Linux virtual machine.

The lab starts with your user account, called analyst, already logged in to a Linux terminal.

Your Linux user's home directory contains a sample packet capture file that you will use at the end of the lab to answer a few questions about the network traffic that it contains.

## Task 1. Identify network interfaces
1. Use `ifconfig` to identify the interfaces that are available:
   This command returns output similar to the following:

<img width="680" alt="Screenshot 2024-09-20 at 11 04 16 AM" src="https://github.com/user-attachments/assets/909322c1-959b-4117-8dd9-6ae37f93ca20">

The Ethernet network interface is identified by the entry with the `eth` prefix.

So, in this lab, you'll use `eth0` as the interface that you will capture network packet data from in the following tasks.
