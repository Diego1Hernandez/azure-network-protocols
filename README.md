<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1 Create Our Resources
- Step 2 Observe Different Types of Traffic

<h2>Actions and Observations</h2>

<h2>Creating Our Resources</h2>

<p>
<img src="https://i.imgur.com/QHRSVO5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Windows 10 Virtual Machine(VM) named "VM1".  Next, create a Linux (Ubuntu) VM named "VM2", select the previously created Resource Group and Vnet when creating this new VM.

</p>
<br />

<h2>Download Wireshark onto VM 1</h2>

<p>
<img src="https://i.imgur.com/CLz2qo0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/BTvFxCw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Connect to your VM1 using Remote Desktop Connection. On VM1 dowload and install wireshark from "https://www.wireshark.org/download.html". 
</p>
<br />

<h2>Creating Inbound Security Rules and Observing ICMP Traffic</h2>

<p>
<img src="https://i.imgur.com/DJ10wms.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/zThSAxL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/EMWQk8U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Wireshark and type "ICMP" into the search bar and press enter. Next, open command line on VM1 through the start menu, then send a perpetual ping command "ping -t <ip address>" to VM2's private IP address. VM2's private IP address can be found on azure Virtual Machines-->VM2-->IPaddress. Traffic should be observable on Wireshark shortly after pinging VM2. Next, on Azure open Network Security Groups-->VM2-NSH-->Inbound Security Rules-->add. Set the designated port ranges to ICMP, then set action to deny. Return to VM1, observe the perpetual ping to VM2 timeout and observe the traffic on wireshark. 
</p>
<br />

<p>
<h2>Observing SSH Traffic</h2>

<p>
<img src="https://i.imgur.com/HIiSY6L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<h2>Observing DHCP Traffic</h2>

<p>
<img src="https://i.imgur.com/AiIuFZG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<h2>Observing DNS and RDP Traffic</h2>

<p>
<img src="https://i.imgur.com/r74f1dL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Tl5308z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
