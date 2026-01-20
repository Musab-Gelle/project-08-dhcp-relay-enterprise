# project-08-dhcp-relay-enterprise
This project demonstrates a realistic enterprise DHCP design where a central DHCP server is hosted at HQ and Branch clients receive IP addresses using DHCP relay (ip helper-address).  This mirrors real-world corporate networks where DHCP is centralised for scalability and control.  

# Network Topology
- HQ Router provides DHCP services for:
  - HR (192.168.10.0/24)
  - IT (192.168.20.0/24)
  - Finance (192.168.30.0/24)
- Branch Router forwards DHCP requests to HQ using `ip helper-address`
- All PCs use **DHCP (no static IPs)**


# IP Addressing Plan

| Network | Purpose |
|-------|--------|
| 192.168.10.0/24 | HR VLAN |
| 192.168.20.0/24 | IT VLAN |
| 192.168.30.0/24 | Finance VLAN |
| 192.168.40.0/24 | Branch LAN |
| 10.0.0.0/24 | HQ ↔ Branch WAN |


# Key Configurations
- Centralised DHCP pools on HQ Router
- DHCP exclusions for gateway addresses
- DHCP relay on Branch Router (`ip helper-address`)
- Static routing between HQ and Branch


# Verification Tests
- All PCs successfully obtain IP addresses via DHCP
- Correct default gateway assigned per subnet
- DNS assigned as 8.8.8.8
- Successful inter-site pings:
  - Branch PC → HR / IT / Finance
  - HQ PCs → Branch PC


# Skills Demonstrated
- DHCP server configuration
- DHCP relay (ip helper-address)
- Enterprise IP addressing
- Static routing
- Layer 3 troubleshooting in Packet Tracer



# Tools Used
- Cisco Packet Tracer
- Cisco IOS CLI
