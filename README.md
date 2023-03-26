<p align="center">
<img src="https://i.imgur.com/J8diUgJ.jpg alt="Traffic Examination"/>
</p>

<h1>VPC Peering on AWS</h1>


<P>
	A VPC Peering Connection is a networking connection between two VPC’s that Enables you to route traffic between them using private IPv4 addresses or Ipv6 addresses.  In this Guide we is cover how to create VPC Peering on AWS.
  </p>
  <br />
  
  <p align="center">
<img src="https://i.imgur.com/ixtEfbT.png alt="Traffic Examination"/>
</p>


<h2>Environments and Technologies Used</h2>

- AWS Account
- Services: VPC(Virtual private cloud) and EC2(Amazon Elastic Compute Cloud)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
<h2>Task summary</h2>


	 
  - Creating two VPC's
  - create one VPC with Workflow create and the other without
  - create/configure a subnet
  - create/configure a route table
  - Create/configure Internet Gateway
  - Create/configure two EC2 instances
  - Create a Peering Connection
   
   
  
  <br />

<h2>Creating the virtual machines<h2/>                                                             

- Step 1.a - Log into AWS Home console

<p>
<img src="https://i.imgur.com/lFkzNFY.png alt"Resource Group"/?
</p>
<br />
<br />

1.b Click on the VPC Service.Then Click create VPC

<p>
<img src="https://i.imgur.com/2kIe3pS.png alt"Resource Group"/?
</p>
<br />
<br />

1.c Configure the VPC

<p>
<img src="https://i.imgur.com/2kIe3pS.png alt"Resource Group"/?
</p>
<br />
<br />

1.d Now we are going to create a subnet for the vpc

<p>
<img src="https://i.imgur.com/sk0KOMx.png alt"Rescource Group"/?
</p>
<br />
<br />

Step 2.a Next we are going to create a Route table. This will help route traffic inside the vpc. click on Rout tables on the left tab menu.  Then you will see a Orange box that says "create a route table".

<p>
<img src="https://i.imgur.com/9i6mGQB.png alt"Rescource Group"/?
</p>
<br />
<br />  

<p>
<img src="https://i.imgur.com/1mpaxhQ.png alt"Rescource Group"/?
</p>
<br />
<br />  
  
2b. Now we are going to create an internet gatway(IGW) inside our VPC.  This is what allows Traffic from the internet to enter our VPC. Note: at this point the IGW is only created in the vpc but not connected to the vpc.
<p>
<img src="https://i.imgur.com/2OxTJgS.png alt"Rescource Group"/?
</p>
<br />
<br /> 

<p>
<img src="https://i.imgur.com/ME7uuBR.png alt"Rescource Group"/?
</p>
<br />
<br /
                                                            
2c. We are now going to be configuring the Internet Gateway to be attached to our VPC. 
<p>
<img src="https://i.imgur.com/krSdl3H.png alt"Rescource Group"/?
</p>
<br />
<br />
  
2d. we are going to be editing our route table so it can start flowing traffic from our vpc to the internet properly
<p>
<img src="https://i.imgur.com/pfXvmZv.png alt"Rescource Group"/?
</p>
<br />                                                            
<br />
                                                            
2e. Now we have to create our second VPC. Repeat earlier steps and go to the VPC tab.  This time after clicking the orange button make sure we check mark the box that says "Create VPC and more". This will Create the Subnet,Route table,internet gatway along with the vpc.  It will also configure them to the vpc as well.                                                           
<p>
<img src="https://i.imgur.com/IFdHMDC.png alt"Rescource Group"/?
</p>

<p>
<img src="https://i.imgur.com/LJ73wG4.png alt"Rescource Group"/?
</p>


Step 3 - Log in to VM1 using it's ip address

<p>
<img src="https://imgur.com/pzsx4Xn.png alt"Rescource Group"/?
</p>

<p>
<img src="https://imgur.com/Hz2NxI2.png alt"Rescource Group"/?
</p>
<br />
<br />  

Step 4 - After logging in to the VM, navigate to Microsoft Edge and install Wireshark 

<p>
<img src="https://imgur.com/clrmTgG.png alt"Rescource Group"/?
</p>

<p>
<img src="https://imgur.com/plnj4UI.png alt"Rescource Group"/?
</p>
<br />
<br />
Now that you have logged in you can continue on to the traffic observation steps detailed below.
<br />
<br />
<br />  


<h2>Actions and Observations</h2>
These observations are made by inputting commands that corresond to the type of traffic one wishes to observe and then filtering Wireshark by the corresponding traffic type.
<br />
<br />

Below is RDP (Remote Desktop Protocol) traffic observation after filtering for RDP traffic in Wireshark 

<p>
<img src="https://imgur.com/CHAA6zi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


Below is DHCP (Dynamic Host Control Protocol) traffic observation using Wireshark

<p>
<img src="https://imgur.com/Gi74JxZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


Below is DNS (Domain Name System) traffic observation using Wireshark

<p>
<img src="https://imgur.com/NQQTI7C.png " height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


Below is SSH (Secure Shell) traffic observation using Wireshark

<p>
<img src="https://imgur.com/2lxIu4v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


Below are the steps for ICMP (nternet Control Message Protocol) traffic observation from a perpetual ping and ICMP traffic stop after the inbound firewall rule is set 
<br />
1. Set the perpetual ping comand to ping VM2 and observe the ICMP traffic
<p>
<img src="https://imgur.com/cgRnPPG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />

2. Change the Inbound firewall rule to deny ICMP traffic

<p>
<img src="https://imgur.com/gKmvkuS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />


3. Observe the ping request times out after the firewall rule was put in place
(*note - The ping request timed out due to the ICMP traffic being denied as the firewall rule blocked the traffic)
<p>
<img src="https://imgur.com/dMWGgWi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h1>Thank Your for looking! For more content like this, visit <a href="https://exemplarysecurity.com">my website</a>☺</h1>
