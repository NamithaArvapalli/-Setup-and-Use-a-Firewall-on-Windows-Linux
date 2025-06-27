# -Setup-and-Use-a-Firewall-on-Windows-Linux
Task-4

Setup and Use a Firewall on Windows/Linux

✅ Objective

Configure and test basic firewall rules to allow or block specific network traffic using:

1.UFW (Uncomplicated Firewall) on Linux

2.Windows Defender Firewall on Windows

🛠️ Tools Used

Linux: UFW

Windows: Windows Defender Firewall with Advanced Security

Port testing tools: telnet, netcat, or nmap

🔍 Part A: Using UFW on Linux (e.g., Ubuntu or Kali)
1. Enable and Check UFW Status
sudo ufw enable
sudo ufw status numbered

3. Block Inbound Traffic on Port 23 (Telnet)
sudo ufw deny 23

5. Test Port 23 Block (From local or remote)
telnet localhost 23
Expected: Connection refused or blocked.

6. Allow SSH Traffic (Port 22)
sudo ufw allow 22

8. Remove the Block Rule on Port 23
sudo ufw delete deny 23

10. List All Current Rules
sudo ufw status verbose

📸 Deliverable (Linux)Take a screenshot of:

sudo ufw status numbered
after steps 2 and 4.

🪟 Part B: Using Windows Defender Firewall
1. Open Firewall Configuration Tool
Press Win + R, type: wf.msc → Enter

2. List/Review Current Rules
In the left panel: Inbound Rules → Check existing rules

3. Create a Block Rule for Port 23
Right-click on Inbound Rules → New Rule

Rule Type: Port

TCP → Specific Port: 23

Action: Block the connection

Profile: All

Name: Block Telnet

4. Test Rule Using Telnet (optional)
telnet 127.0.0.1 23
Expected: Connection failed

5. Allow SSH (if using SSH server on Windows)
Create a new rule:

Port: 22 → Allow the connection

6. Remove Block Rule
Find Block Telnet in Inbound Rules, right-click → Delete

📸 Deliverable (Windows)
Take a screenshot of:

The Inbound Rule list showing the created Block Telnet rule.

🧾 Summary: How Firewalls Filter Traffic
Firewalls inspect incoming and outgoing traffic based on a defined set of rules. They:

Allow or deny packets based on IP, port, or protocol

Help prevent unauthorized access

Essential for network segmentation and protection

For example:

Blocking Telnet (port 23) helps prevent outdated, unencrypted access.

Allowing SSH (port 22) permits secure remote administration.
