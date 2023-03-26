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

                                                           

- Step 1. - Log into AWS Home console

<p>
<img src="https://i.imgur.com/lFkzNFY.png alt"Resource Group"/?
</p>
<br />
<br />

Step.2 Click on the VPC Service.Then Click create VPC

<p>
<img src="https://i.imgur.com/2kIe3pS.png alt"Resource Group"/?
</p>
<br />
<br />

step.3 Configure the VPC

<p>
<img src="https://i.imgur.com/2kIe3pS.png alt"Resource Group"/?
</p>
<br />
<br />

step.4 Now we are going to create a subnet for the vpc.

<p>
<img src="https://i.imgur.com/sk0KOMx.png alt"Rescource Group"/?
</p>
<br />
<br />

step.6 Next we are going to create a Route table. This will help route traffic inside the vpc. click on Rout tables on the left tab menu.  Then you will see a Orange box that says "create a route table".

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
  
Step.7 Now we are going to create an internet gatway(IGW) inside our VPC.  This is what allows Traffic from the internet to enter our VPC. Note: at this point the IGW is only created in the vpc but not connected to the vpc.
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
                                                            
Step.8 We are now going to be configuring the Internet Gateway to be attached to our VPC. 
<p>
<img src="https://i.imgur.com/krSdl3H.png alt"Rescource Group"/?
</p>
<br />
<br />
  
Step.9 we are going to be editing our route table so it can start flowing traffic from our vpc to the internet properly
<p>
<img src="https://i.imgur.com/pfXvmZv.png alt"Rescource Group"/?
</p>
<br />                                                            
<br />
                                                            
Step.10 Now we have to create our second VPC. Repeat earlier steps and go to the VPC tab.  This time after clicking the orange button make sure we check mark the box that says "Create VPC and more". This will Create the Subnet,Route table,internet gatway along with the vpc.  It will also configure them to the vpc as well.                                                           
<p>
<img src="https://i.imgur.com/IFdHMDC.png alt"Rescource Group"/?
</p>

<p>
<img src="https://i.imgur.com/LJ73wG4.png alt"Rescource Group"/?
</p>


Step.11 - Now can Can Create our Ec2 instance's. We will be making 1 for each VPC

<p>
<img src="https://i.imgur.com/a2rZN7O.png alt"Rescource Group"/?
</p>

<p>
<img src="https://i.imgur.com/iw1AQFD.png alt"Rescource Group"/?
</p>
<br />
<br />  

<p>
<img src="https://i.imgur.com/Qukc7oG.png alt"Rescource Group"/?
</p>
<br />
<br />  

Step.12 - Now we can create the peering connection between the VPC's.  Under the VPC tab you will see "Peering connection". Once we configure.  VPC one will send a request to VPC2 for it to accept the Peering connection.

<p>
<img src="https://i.imgur.com/vHEzXMR.png alt"Rescource Group"/?
</p>

<p>
<img src="https://i.imgur.com/sWLEIKU.png alt"Rescource Group"/?
</p>
<br />
<br />
Step.13 -  Now we have to edit our route tables on each VPC so not traffic will flow back and forth between the VPC's.
<br />
<br />
<br />  


<p>
<img src="https://i.imgur.com/1NAgkMH.png alt"Rescource Group"/?
</p>
<br />
<br /> 

<br />

Step.15 Finally We will be setting up a Reachability analyzer path. This will scan the path that we have created between the two vpc and check if the path is still good or if a route error has accord. NOTE:  You can also achive the same results by conneting into you instances that you have made and pinging them  against each other.

<p>
<img src="https://i.imgur.com/oXkaPjT.png alt"Rescource Group"/?
</p>
<br />
<br />  

Success!  We have finished pairing our two VPC's That we created.

<p>
<img src="https://i.imgur.com/BxG3atb.png alt"Rescource Group"/?
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/seyhc9B.jpg alt"Rescource Group"/?
</p>
<br />
<br /> 	
	
	
	

