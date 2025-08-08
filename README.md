 <div align="center">
  
  # Setup and Use a Firewall on Windows

 </div>

 Date - 08 august 2025

 Submitted By - PRADEEP S
 
--

## 🎯 Objective
         
   To configure and test basic inbound firewall rules on Windows by blocking Telnet (port 23) and allowing SSH (port 22), demonstrating understanding of network traffic filter.
     
## 🔍 Summary: How a Firewall Filters Traffic
               
   A firewall acts as a barrier between a trusted internal network and untrusted external networks (like the internet). It filters network traffic based on a set of predefined rules.

 Here's how it works:

   🔐 Inbound Rules: Control what kind of traffic is allowed into your system 

   📤 Outbound Rules: Control what traffic is allowed to leave your system 

   The firewall evaluates each incoming or outgoing packet and either:

   * Allows it — if it matches a permitted rule.

   * Blocks it — if it matches a deny rule or doesn't match any allowed rules.


## 🛠️ Tools Used
         
   * Windows Defender Firewall
   * telnet Client (Windows feature)
   * Command Prompt (cmd)
   * Open ssh Server (Windows Features)

## 🔄 Steps Summary(Windows)
  
  1.Opened windows defender firewall with advanced security.
        * Accessed via Control Panel >Windows Defender Firewall>Advanced Settings.
       
  2.Created Inbound Rule to block Port 23 (Telnet)
         
   * Rule Type - port
   * Protocol - TCP
   * port - 23
   * Action - Block The Connection
   * Profile - Domain, private, public
   * Name - Block_telnet_23
 
 3.Created Inbound Rule to Allow Port 22 (SSH)
       
   * Rule Type - port
   * Protocol - TCP
   * port - 22
   * Action - Allow The Connection
   * Profile - Domain, private, public
   * Name - Allow_ssh_22

 4.Verified firewall Rules
          
   * Confirmed both rules are listed and enabled under Inbound Rules
 
 5.tested with Telnet

   * Ran Telnet localhost 23 > Connection failed (port blocked as expected)
   * Ran Telnet localhost 22 > connection failed 
                   
     Expected, since SSH service is not running, but port is allowed in firewall. because  Windows does not run SSH server by default, unless you manually install and start it.
                 
     So, the firewall allowed port 22, but no application is listening ,so the connection fails. this is not a firewall problem, its a missing service. 
           
 6.Commands  are used in Windows
    * For enable Telnet in optional feature press win+R and enter optional features. after opened scroll down and enable Telnet.
    * telnet localhost 23 (Telnet)
    * telnet localhost 22 (SSH)

## 📌 Windows Defender Firewall Configuration
 <img width="1919" height="1027" alt="Screenshot 2025-08-08 120019" src="https://github.com/user-attachments/assets/73c16e63-3320-4fcc-ab82-819cd9ce98c5" />

## 📌 Command Prompt (cmd) – Telnet Test Results
 <img width="1919" height="1032" alt="Screenshot 2025-08-08 120104" src="https://github.com/user-attachments/assets/729502ea-a326-434b-a3a0-3d73c4d3281f" />

## 🐧Firewall Configuration & Testing on Kali Linux

# 🛠️ Tools Used
          
   * UFW (Uncomplicated Firewall) – To configure firewall rules

   * Telnet Client – To test port accessibility

   * Command Line (Terminal) – For executing firewall and network commands

   * Netstat – To check open/listening ports
 
## ⚙️ Setup Summary
 
   1.Enable ufw firewall - sudo ufw enable
   2.Allowed SSH (port 22) - sudo ufw allow 22/tcp
   3.Blocked Telnet (port 23) - sudo ufw deny 23/tcp
   4.Verified firewall rules - sudo ufw status numbered / sudo ufw status verbose           
           

## 🧪 Firewall Testing (Telnet Results)


| Test Command          | Expected Result              | Actual Output                                | Status     |
| --------------------- | ---------------------------- | -------------------------------------------- | --------   |
|  telnet localhost 22  | Connect if SSH is running    | Connection refused (service not running)     | ✅ Correct |
|  telnet localhost 23  | Connection refused (blocked) | Connection refused                           | ✅ Correct |


## 📌 UFW Status Showing Applied Rules and UFW Enable Output

<img width="1919" height="965" alt="Screenshot 2025-08-08 133017" src="https://github.com/user-attachments/assets/1f8c8e0e-40e4-42b8-8a66-d03478293843" />


## 📌 Telnet Test Results

<img width="1919" height="1034" alt="Screenshot 2025-08-08 133138" src="https://github.com/user-attachments/assets/c66362d6-09b0-42b6-ba43-c5a1f206a1cf" />















          
      
         
         
         

            
