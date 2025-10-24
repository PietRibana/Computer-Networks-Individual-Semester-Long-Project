📘 Project Overview

This project demonstrates how to configure VTP (VLAN Trunking Protocol) Transparent Mode on a Cisco switch using Cisco Packet Tracer.
VTP is used to manage VLAN information across multiple switches within the same domain. In transparent mode, a switch does not participate in VTP advertisements but still forwards them to other switches.

🧩 Network Topology

Switch0 → VTP Server

Switch1 → VTP Client

Switch2 → VTP Transparent Mode

Connections:

Switch0 (Fa0/1) ↔ Switch1 (Fa0/1)

Switch0 (Fa0/2) ↔ Switch2 (Fa0/1)

⚙️ Configuration Steps
Step 1: Set Hostnames
Switch> enable
Switch# configure terminal
Switch(config)# hostname Switch2

Step 2: Configure VTP on Switch2 (Transparent Mode)
Switch2(config)# vtp domain XYZ
Switch2(config)# vtp mode transparent
Switch2(config)# vtp version 2


You should see:

Setting device to VTP TRANSPARENT mode.

Step 3: Create Local VLANs (Optional)
Switch2(config)# vlan 50
Switch2(config-vlan)# name HR
Switch2(config)# vlan 60
Switch2(config-vlan)# name Finance

Step 4: Verify Configuration
Switch2# show vtp status


Expected Output:

VTP Operating Mode              : Transparent
VTP Domain Name                 : XYZ
Configuration Revision          : 0
Number of existing VLANs        : 5

🧠 Key Notes

Transparent switches do not synchronize VLAN information from other switches.

VLANs created locally on a transparent switch are not advertised to others.

The switch forwards VTP advertisements but does not act on them.

🧾 Commands Summary
Command	Description
vtp domain [name]	Set the VTP domain name
vtp mode transparent	Configure switch as transparent
vtp version 2	Set VTP version
show vtp status	Verify VTP configuration
📄 File Information

Filename: VTP_TransparentMode.pkt
Created with: Cisco Packet Tracer 8.x
Author: Kgomotso Piet Ribana
Date: 13 October 2025

✅ Conclusion

This project demonstrates how to isolate a switch from VTP synchronization while maintaining its ability to forward advertisements. VTP Transparent Mode is ideal for independent VLAN management in segmented network environments.
