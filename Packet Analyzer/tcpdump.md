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

2. Use tcpdump to identify the interface options available for packet capture:
This command will also allow you to identify which network interfaces are available. This may be useful on systems that do not include the `ifconfig` command.

<img width="657" alt="Screenshot 2024-09-20 at 11 04 25 AM" src="https://github.com/user-attachments/assets/87eb65e4-01a7-4ea1-956d-2487e461a606">

## Task 2. Inspect the network traffic of a network interface with tcpdump
In this task, you must use `tcpdump` to filter live network packet traffic on an interface.
Filter live network packet data from the `eth0` interface with `tcpdump`:
This command will run tcpdump with the following options:

- `i eth0`: Capture data specifically from the eth0 interface.
- `v`: Display detailed packet data.
- `c5`: Capture 5 packets of data.
<img width="715" alt="Screenshot 2024-09-20 at 11 12 04 AM" src="https://github.com/user-attachments/assets/639da073-bf14-4f62-8bea-f17001622323">

### Exploring network packet details


