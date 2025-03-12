# Home-Lab-Setup-SOC With Splunk
Home SOC Lab – Security Monitoring & Threat Detection

📌 Overview

This project sets up a Home SOC (Security Operations Center) Lab to simulate real-world security monitoring, log analysis, and threat detection. It utilizes Splunk on Kali Linux as the SIEM platform and Splunk Universal Forwarder on Windows 10 for log forwarding.
🛠️ Technologies Used

    Virtualization: VirtualBox
    Operating Systems: Kali Linux, Windows 10
    SIEM Solution: Splunk
    Log Forwarding: Splunk Universal Forwarder
    
  ⚡ Features

    Centralized Log Management: Collects and analyzes logs from Windows machines.
    Real-time Monitoring: Detects suspicious activities and security events.
    Automated Log Forwarding: Uses Splunk Universal Forwarder to send logs to the SIEM.
    
  🚀 Installation Steps

    1.Set Up Virtual Machines
      Install Kali Linux and Windows 10 in VirtualBox.

    2.Install Splunk on Kali Linux

    3.Install & Configure Splunk Universal Forwarder on Windows 10
      Download and install the Splunk Universal Forwarder.
      Configure it to forward logs to Splunk on Kali.
       
    4.Set Up Log Forwarding
      Configure inputs.conf and outputs.conf to enable log collection.

    5.Enable Security Alerts
      Use Splunk queries to detect threats and anomalies.

  Home SOC Lab - Step-by-Step Setup Guide

  Step 1: Prepare Your Virtual Environment   
  
        To create an isolated SOC lab, use VirtualBox or VMware to set up multiple virtual machines.

        🔹 Kali Linux (SIEM Server) – Install Splunk for centralized log analysis.
        🔹 Windows 10/11 (Client System) – Install Splunk Universal Forwarder to send logs to the SIEM.

   Step 2: Install Splunk on Kali Linux
                
        1️⃣ Download Splunk
        Run the following command in Kali Linux to download Splunk:

```bash
        wget -O splunk.deb https://download.splunk.com/products/splunk/releases/9.0.3/linux/splunk-9.0.3-amd64.deb
```
        2️⃣ Install Splunk
        Use dpkg to install it:
   
```bash
        sudo dpkg -i splunk.deb
```
        3️⃣ Start Splunk and Accept the License
        
```bash
        sudo /opt/splunk/bin/splunk start --accept-license
```
        4️⃣ Enable Splunk to Start on Boot
```bash
        sudo /opt/splunk/bin/splunk enable boot-start
```
        5️⃣ Access Splunk Web UI
        Open a browser and go to:
        
```bash
        http://localhost:8000
```
        Login with:
        Username: splunk_admin
        Password: (Set during setup) 
        
   Step 3: Install Splunk Universal Forwarder on Windows


   The Universal Forwarder sends logs from Windows to your Splunk SIEM.
        
        1️⃣ Download and Install Forwarder
        
        Download the Splunk Universal Forwarder from Splunk Downloads.
        Install it using default settings.
        Set up a user account for Splunk.

        2️⃣ Connect the Forwarder to the Splunk Server
        
        Open Command Prompt as Administrator.
        Run this command (replace <Kali-IP> with your actual Kali Linux IP):

```bash
        splunk add forward-server <Kali-IP>:9997 -auth admin:changeme
```
        Enable log forwarding:

```bash
        splunk enable boot-start
```
        Restart the forwarder:
```bash
        splunk restart
```

   Step 4: Configure Data Inputs in Splunk

    Login to Splunk Web UI on Kali Linux (http://localhost:8000).
    Go to Settings > Data Inputs.
    Add a new TCP/UDP input and set the port to 9997.
    Check if logs are received from the Windows Forwarder using:

```bash
    index=_internal | stats count by host
```

  Step 6: Test the Home SOC Lab
        


        
  
