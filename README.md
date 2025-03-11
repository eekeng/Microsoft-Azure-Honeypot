<h1>Microsoft Azure Honeypot</h1>


<h2>Description</h2>
In this project, I configured a virtual machine on Microsoft Azure to function as a Honeypot, specifically targeting Remote Desktop Protocol (RDP) attacks. I then utilized Log Analytics Workspace to extract and analyze metadata from failed login attempts, converting it into geographic data, including latitude, longitude, state/province, and country. Finally, I visualized this data using Microsoft Sentinel, mapping the attack origins to gain insights into potential threat sources.

<br />


<h2>Tools Used</h2>

- <b>Microsoft Azure</b> 
- <b>Microsoft Sentinel</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 

<h2>Walk-through:</h2>

<p align="center">
Create a resource group, virtual network, and a virtual machine in Microsoft Azure: <br/>
<img src="https://i.imgur.com/GQtQvzZ.png" height="80%" width="80%" "/>
<br />
<br />
Modify the VM’s inbound security rules to allow all traffic (intentionally reducing security to attract attackers for the Honeypot):  <br/>
<img src="https://i.imgur.com/wfa4ybC.png" height="80%" width="80%" "/>
<br />
<br />
Connect to the VM via RDP and disable its internal firewall: <br/>
<img src="https://i.imgur.com/UwolgJY.png" height="80%" width="80%" "/>
<br />
<br />
Set up a Log Analytics Workspace in Azure:  <br/>
<img src="https://i.imgur.com/iw0Lowd.png" height="80%" width="80%" "/>
<br />
<br />
Add Microsoft Sentinel to the workspace:  <br/>
<img src="https://i.imgur.com/hX4P1a9.png" height="80%" width="80%" "/>
<br />
<br />
In Microsoft Sentinel, install Windows Security Events:  <br/>
<img src="https://i.imgur.com/0JnN2qE.png" height="80%" width="80%" "/>
<br />
<br />
Enable Windows Security Events via AMA (Azure Monitor Agent):  <br/>
<img src="https://i.imgur.com/0JnN2qE.png" height="80%" width="80%" "/>
<br />
<br />
Create a Data Collection Rule within Windows Security Events via AMA:  <br/>
<img src="https://i.imgur.com/VaBQ4jP.png" height="80%" width="80%" "/>
<br />
<br />
In Sentinel, navigate to Watchlists and create a new watchlist:  <br/>
<img src="https://i.imgur.com/7LAnNjS.png" height="80%" width="80%" "/>
<br />
<br />
Upload the GeoIP file:  <br/>
<img src="https://i.imgur.com/O9U1I6l.png" height="80%" width="80%" "/>
<br />
<br />
In Sentinel, go to Workbooks, create a new workbook, and select Add Query:  <br/>
<img src="https://i.imgur.com/ni8bUOv.png" height="80%" width="80%" "/>
<br />
<br />
Open the Advanced Editor and insert the provided script:  <br/>
<img src="https://i.imgur.com/olBk6yy.png" height="80%" width="80%" "/>
<br />
<br />
A world map displaying all failed RDP attempts is now generated! 😊:  <br/>
<img src="https://i.imgur.com/CyZ5o02.png" height="80%" width="80%" "/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
