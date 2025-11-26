# ARP Spoofing with Scapy

A Python implementation of ARP spoofing (ARP poisoning) attack using the Scapy library. This tool intercepts network traffic between two devices on a local network.
<img width="1918" height="1078" alt="Vérifier la table ARP AVANT l’attaque (Windows)" src="https://github.com/user-attachments/assets/4c91c856-3677-4b94-b926-7c1937c832bf" />


## ⚠️ Legal Disclaimer

**This tool is for educational and authorized security testing purposes only.** Unauthorized network attacks are illegal and unethical. Always:
- Obtain written permission before testing
- Only use on networks you own or have explicit authorization to test
- Comply with local and international laws

## 📋 Prerequisites

- Python 3.x
- Scapy library
- Administrator/Root privileges
- Linux, macOS, or Windows with Npcap installed

## 🔧 Installation

1. Clone the repository:
```bash
git clone https://github.com/YOUR_USERNAME/arp-spoofing-scapy.git
cd arp-spoofing-scapy
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

Or install Scapy directly:
```bash
pip install scapy
```

## 🚀 Usage

Run the script with administrator/root privileges:

```bash
sudo python3 arp_spoof.py -t <target_ip> -g <gateway_ip>
```

### Arguments:
- `-t, --target`: Target IP address (e.g., 192.168.1.100)
- `-g, --gateway`: Gateway IP address (e.g., 192.168.1.1)

### Example:
```bash
sudo python3 arp_spoof.py -t 192.168.1.100 -g 192.168.1.1
```

Press `Ctrl+C` to stop the attack and restore ARP tables.

## 📝 How it Works

1. **ARP Resolution**: Gets MAC addresses for target and gateway IPs
2. **ARP Spoofing**: Sends fake ARP replies to both target and gateway
3. **Traffic Interception**: Redirects traffic between target and gateway through the attacker
4. **Restoration**: On exit, sends legitimate ARP packets to restore normal operation

## 🔍 Functions

- `get_mac(ip)`: Resolves IP address to MAC address
- `spoof(target_ip, spoof_ip)`: Sends spoofed ARP packets
- `restore(destination_ip, source_ip)`: Restores ARP tables

## 📦 Dependencies

- **scapy**: Network packet crafting and manipulation

## 🎓 Educational Use

This project is ideal for learning about:
- ARP protocol and vulnerabilities
- Network security concepts
- Packet crafting with Scapy
- Man-in-the-middle (MITM) attacks

## 🔐 Mitigation

To protect against ARP spoofing:
- Use static ARP entries
- Enable ARP inspection on switches
- Use VPNs or encrypted communications
- Implement network segmentation
- Use DHCP snooping

## 📄 License

MIT License - See LICENSE file for details

## 🤝 Contributing

Contributions are welcome! Please ensure:
- Code follows PEP 8 style guide
- Add comments for complex logic
- Include docstrings for functions

## ⚠️ Troubleshooting

**Permission Denied**: Run with `sudo` (Linux/macOS) or as Administrator (Windows)

**Scapy not found**: Install with `pip install scapy`

**MAC address not found**: Ensure the IP is on the same network

**Npcap error (Windows)**: Install Npcap from https://nmap.org/npcap/

## 📚 References

- [Scapy Documentation](https://scapy.readthedocs.io/)
- [ARP Protocol (RFC 826)](https://tools.ietf.org/html/rfc826)
- [MITM Attack Concepts](https://en.wikipedia.org/wiki/Man-in-the-middle_attack)

---

**Remember**: Use this tool responsibly and legally!
