# NETWORKWALKS B083B Week 1 - Cybersecurity Internship

## Lab: Kali Linux Network Setup (PM1)

*Official Architecture Verified ✅*
- Network Name: NatNetwork
- Subnet: 10.0.0.0/24
- Gateway: 10.0.0.1
- Kali IP: 10.0.0.2/24
- DNS: 8.8.8.8
- Snapshot: Baseline_Week1_Clean

### Steps Completed

*1. VirtualBox NAT Network Creation*
File > Tools > Network Manager > NAT Networks > Create
- Name: NatNetwork
- CIDR: 10.0.0.0/24
- Gateway: 10.0.0.1
- DHCP: Enabled

*2. Kali Adapter Config*
Settings > Network > Adapter 1 > Attached to: NAT Network > NatNetwork

*3. Static IP Configuration*
```bash
sudo nmcli connection modify "Wired connection 1" ipv4.addresses 10.0.0.2/24 ipv4.gateway 10.0.0.1 ipv4.dns 8.8.8.8 ipv4.method manual
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
sudo nmcli connection down "Wired connection 1" && sudo nmcli connection up "Wired connection 1"
