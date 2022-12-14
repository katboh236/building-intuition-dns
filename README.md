<p align="center">
<img src="https://i.imgur.com/CtGfsq8.png" alt="osTicket logo"/>
</p>

<h1>Building Intuition for DNS</h1>
In this lab we will be experimenting with DNS. This lab will help us have a better understanding of DNS.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- DNS

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Active Directory running i Azure on a Virtual Machine (DC-1 - Domain Controller)
- Client Machine running in Azure on a Virtual Machine (Client-1) and joined to the domain

<h2>High-Level Deployment and Configuration Steps</h2>

- Inspect DNS A-Records on the server (hostname to IP address mappings)
- Local DNS Cache Exercise
- CHAME Record Exercise

<h2>Deployment and Configuration Steps</h2>
<p>
</p>
<p>
<img src="https://imgur.com/2FFxTSw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://imgur.com/zASiK84.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Connected into DC-1 and Client-1 as my admin account, created a DNS A-record on DC-1 for "mainframe" and had it point to DC-1's Private IP address, went back to Client-1, pinged it and observed that it works.
</p>
<br />
<p>
<img src="https://imgur.com/Z8a5rN8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://imgur.com/V4KWSOc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://imgur.com/GX4PPhj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Went back to DC-1 and changed mainframe's record address to 8.8.8.8, went back to Client-1, pinged "mainframe" again - still pinged the old address. In order to observe the new address, I flushed the DNS cache (ipconfig /flushdns), observed that cache was empty, pinged "mainframe" again and observed the address of the new record is showing up.
</p>
<br />
<p>
<img src="https://imgur.com/LkC6XLU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Created a CNAME record on DC-1 that points the host "search" to "www.google.com", went back to Client-1 and attempted to ping "search" of the CNAME record. Observed the results of the CNAME record on Client-1 (nslookup "search") which showed that we can map names to other names.
</p>
<br />
