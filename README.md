# Multi-Branch-Network-Troubleshooting

<p align="center">
<img src="https://i.imgur.com/vf3Hyav.png" height="80%" width="80%"/>
</p>

<h2>Project Overview</h2>
<p> This project documents the troubleshooting and restoration of network
connectivity across a preconfigured multi-branch topology in Cisco Packet
Tracer.
</p>
<p>The environment consisted of three branch routers connected through a
central Core router. Each branch supported a separate LAN and workstation.
The initial configuration prevented successful communication between devices
located on different branch networks.
</p>
<p>Connectivity was restored by correcting interface addressing, configuring
summarized static routes, assigning valid workstation network settings, and
verifying communication through staged ICMP testing.
</p>

<br>


<h2> Multi-Branch-Network-Troubleshooting Lab </h2>

<p>
<img src="https://i.imgur.com/2XWYZNE.png" height="80%" width="80%"/>
</p>

<p>
<img src="https://i.imgur.com/3fOdZWF.png" height="80%" width="80%"/>
</p>

 

<h2> Troubleshooting Process </h2>
<h3> 1. Documented the Network Interfaces </h3>
<p>  The IP addresses assigned to each router interface were documented to provide
a clear view of the network layout and identify addressing inconsistencies.</p>
 

<p>
<img src="https://i.imgur.com/vf3Hyav.png"height="80%" width="80%" "/> </p>

<br>

<h3> 2. Corrected the Core Router Serial Interface
</h3>

<p>The Core router's 'Serial0/1/0' interface was initially configured with the
following address:</p>
<p>
<img src="https://i.imgur.com/6Oc6mHW.png"height="80%" width="80%" "/>
</p>
<br>


<p> The address was removed and replaced with 10.1.1.1/30, placing the Core
interface in the same point-to-point subnet as the connected Branch 1 router.

</p>

<p>
 <img src="https://i.imgur.com/YPQ8bBv.png" height="80%" width="80%"/> </p>


<p>
This corrected the Layer 3 addressing mismatch on the Core-to-Branch 1
connection.</p>



<br>

<h3>3. Configured Static Summary Routes for the WAN Networks</h3>

<p>Summary routes were configured on Branch 2 and Branch 3 to direct traffic for
remote 10.1.x.x networks toward the Core router.
</p>

<h4> Branch 2: </h4>
<p>
<img src="https://i.imgur.com/oel96KN.png" height="80%" width="80%"/>
</p>
<br>
<h4> Branch 3: </h4>



<p>
<img src="https://i.imgur.com/OCdKPtP.png"height="80%" width="80%" "/>
</p>
<br>
<p> Router-to-router connectivity was then tested. The ICMP test completed with a
100 percent success rate. </p>
<p>
<img src="https://i.imgur.com/UFZRUTa.png"height="80%" width="80%" "/>
</p>
<br>
<h3> 4. Configured the Branch Workstations</h3>
<p> Each workstation was assigned a static IPv4 address, subnet mask, and default
gateway corresponding to its local branch network.
<p>
  <p> The addressing configuration ensured that traffic destined for remote
networks would be forwarded to the correct branch router.
<p>
    <h4> PC0:
</h4>
<img src="https://i.imgur.com/DcCtx5L.png"height="80%" width="80%" "/> </p>
<br>

<h4>PC1:</h4> 


  <p><img src="https://i.imgur.com/NXQprZG.png" height="80%" width="80%"/>
</p>
<br>

<h4>PC2:</h4> 


  <p><img src="https://i.imgur.com/v1s2BPI.png" height="80%" width="80%"/>
</p>
<br>
<h3> 5. Verified Local Gateway Connectivity </h3>

<p> Each workstation was tested against its local default gateway.</p>
<p>
    <h4> PC0 pinging router 2:
</h4>

 <p><img src="https://i.imgur.com/kWsvM0q.png" height="80%" width="80%"/>
</p>
<br>
<h4>PC1 pinging router 3: </h4>
  <p><img src="https://i.imgur.com/vOY1ooF.png" height="80%" width="80%"/>
</p>
 <br>
 <h4>PC2 pinging router 0: </h4>
  <p><img src="https://i.imgur.com/bCbvRjE.png" height="80%" width="80%"/>
</p>

<p>All three tests completed successfully.</p>
<br>

<h3>6. Configured Static Summary Routes for the Branch LANs</h3>
<p> Branch 2 and Branch 3 required routes for the remote 192.168.x.x branch
networks.</p>
 <h4> Branch 2:
</h4>

 <p><img src="https://i.imgur.com/xBaVY0n.png" height="80%" width="80%"/>
</p>

<br>
 <h4> Branch 3:
</h4>

 <p><img src="https://i.imgur.com/OmJgQBu.png" height="80%" width="80%"/>
</p>


<p>The summary routes directed traffic for remote branch LANs toward the Core
router while allowing each branch router to continue using its directly
connected route for the local LAN.</p>
<h3> 7. Connectivity Validation </h3>

 <h4> PC0 pinging PC1:
</h4>

 <p><img src="https://i.imgur.com/Tq1HApA.png" height="80%" width="80%"/>
</p>

<br>
<h4> PC2 pinging PC0:
</h4>

 <p><img src="https://i.imgur.com/Tq1HApA.png" height="80%" width="80%"/>
</p>

<br>

 <h2> Resolution 
</h2>
<p>Connectivity was restored by addressing multiple Layer 3 configuration
requirements:</p>
<ul>
  <li>Corrected the Core router's serial interface address</li>
  <li>Configured summarized routes for remote WAN networks</li>
  <li>Assigned valid IPv4 settings to each workstation</li>
    <li>Configured summarized routes for the remote branch LANs</li>
    <li>Verified local and end-to-end communication using ICMP</li>
</ul>  


 <h2> Skills Demonstrated
</h2>

<ul>
  <li>Cisco IOS configuration</li>
  <li>IPv4 addressing and subnetting</li>
  <li>Static routing</li>
    <li>Route summarization</li>
    <li>Default-gateway configuration</li>
   <li>Multi-router connectivity troubleshooting</li>
   <li>Layer 3 path analysis</li>
     <li>ICMP testing and validation</li>
     <li>Cisco Packet Tracer/li>
</ul>  




