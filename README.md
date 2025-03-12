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

      
  
