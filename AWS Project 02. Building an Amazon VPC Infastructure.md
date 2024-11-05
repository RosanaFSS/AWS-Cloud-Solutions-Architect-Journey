<h1> -----  in progress  --- </h1>
<h1>AWS, Building an Amazon VPC infrastructure</h1>
<p>November 4, 2024<br></p>


<p>Hey there, fellow lifelong learner! I´m <a href="https://www.linkedin.com/in/rosanafssantos/">Rosana</a>, and I’m genuinely excited to join you on this adventure. It´s key part of my AWS hands-on journey. Let´s get started!!</p>

<h1 align="center"> $$\textcolor{white}{\textnormal{Objectives}}$$ </h1>
<ul style="list-style-type:square">
    <li>Create an Amazon VPC in a Region.</li>
    <li>Create public and private subnets.</li>
    <li>Create an Internet gateway.</li>
    <li>Route intern traffic in the public subnet to the Internet gateway.</li>
    <li>Create a public Security Group.</li>
    <li>Launch an Amazon EC2 instance into a public subnet.</li>
    <li>Connect to a public instance through HTTP.</li>
    <li>Connect to the Amazon EC2 instance in the public subnet through Session Manager.</li>
    <li>Create a NAT gateway and configure routing in the private subnet.</li>
    <li>Test connectivity to the private instance from the public instance.</li>
    <li>Retrieve instance metadata</li>
    <li>Understand the basic of IPv6 networking on AWS</li>
    <li></li>
</ul></p><br>



<h1 align="center"> $$\textcolor{orange}{\textnormal{Task 1. Create an Amazon VPC in a Region}}$$<a id='1'></a></h1>
<p align="center">In this task, we will create a new Amazon VPC in the AWS Cloud. </p>

<p align="center">With <code>Amazon VPC</code>, you can provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address ranges, creation of subnets, and configuration of route tables and network gateways. You can also use the enhanced security options in Amazon VPC to provide more granular access to and from the Amazon EC2 instances in your virtual network.</p>

<p align="center">  <img width="200px" src="https://github.com/user-attachments/assets/e9d7e6cc-6dc6-4b9f-8fb8-3db3a670babe"> </p>

   <p>- 01 - At the top of the <code>AWS Managememt Console</code>, in the search bar, search for and choose <code>VPC</code>.</p>
   <p>- 02 - In the left navigation pane, choose <code>Your VPCs</code>.</p>
   <p>- 03 - Choose <code>Create VPC</code> and configure the following:</p>
<ul style="list-style-type:square">
    <li>Resources to create: Choose  VPC only.</li>
    <li>Name tag - optional: Enter Lab VPC.</li>
    <li>Pv4 CIDR: Enter 10.0.0.0/16./li>
</ul>
   <p>- 04 - Choose <code>Create VPC</code>.</p>

<h2 align="center"> $$\textcolor{white}{\textnormal{VPC created successfully.}}$$ </h2>

<p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/3a3eeffe-25de-4182-ae7a-902c6b6ec910"> </p><br>

   <p>- 05 - Verify the state of the <code>VPC</code> created.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{VPC is available!}}$$ </h2>

<p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/b2a54727-ea73-4aba-9042-73e593955e08"> </p>

   <p>- 06 - From the same page, choose <code>Actions</code>code> and choose <code>Edit VPC SettingsVPC</code>.</p>
   <p>- 07 - From the <code>DNS settings</code> section, select <code>Enable DNS hostnames</code>.</p>
   <p>- 08 - Choose <code>Save</code>.</p>

<p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/103bfb20-842b-4977-80c0-69ac3ab34fef"> </p>

<p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/d9f72f65-af6f-4092-a540-6c68b0114e17"> </p>

<h2 align="center"> $$\textcolor{white}{\textnormal{VPC settings modified successfully.}}$$ </h2>
<p align="center"> Any Amazon EC2 instances launched into this Amazon VPC now automatically receive a DNS hostname. You can also create a more meaningful DNS name (for example, app.company.com) using records in Amazon Route 53. </p><br>

<h2 align="center"> $$\textcolor{white}{\textnormal{Congratulations! You have successfully created your own VPC}}$$
$$\textcolor{white}{\textnormal{and now you can launch the AWS resources in this defined virtual network.}}$$</h2><br>

<h1 align="center"> $$\textcolor{orange}{\textnormal{Task 2. Create public and private subnets}}$$<a id='2'></a></h1>
<p align="center">In this task, you create a public subnet and a private subnet in the lab VPC. To add a new subnet to your VPC, you must specify an IPv4 CIDR block for the subnet from the range of your VPC. You can specify the Availability Zone in which you want the subnet to reside. You can have multiple subnets in the same Availability Zone. </p>

<p align="center">  <img width="200px" src="https://github.com/user-attachments/assets/81b525d4-c4fc-43ee-9e1b-dacdea06c22c"> </p>

<p align="center">Note: A subnet is a sub-range of IP addresses within a network. You can launch AWS resources into a specified subnet. Use a public subnet for resources that must be connected to the internet, and use a private subnet for resources that are to remain isolated from the internet. </p>

   <p>- 09 - In the left navigation pane, choose <code>Subnets</code>.</p>
   <p>- 10 - Choose <code>Create subnet</code> and configure the following:</p>
<ul style="list-style-type:square">
    <li><code>VPC ID</code>: select Lab VPC from the dropdown menu.</li>
    <li><code>Subnet name</code>: enter Public Subnet.</li>
    <li><code>Availability Zone</code>: select the first Availability Zone in the list. (Do not choose No Preference.)</li>
    <li><code>IPV4 CIDR</code> block: enter 10.0.0.0/24.</li>
</ul>
   <p>- 11 - Choose <code>Create subnet</code>.</p>

   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/341fc24f-9d8c-404b-a2c2-33bcc087e277"> </p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Public subnet created successfully!}}$$ </h2>

   <p>- 12 - Verify the state of the private subnet created.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Public Subnet available!}}$$ </h2>

   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/1282c920-bfb4-43db-b790-a5aae714c055"> </p>

   <p>- 13 - Select <code>Public Subnet</code>.</p>
   <p>- 14 - Choose <code>Actions</code> and choose <code>Edit subnet settings</code>.</p>
   <p>- 15 - From the <code>Auto-assign IP settings</code> section, select <code>Enable auto-assign public IPv4 address</code>.</p>
   <p>- 16 - Choose <code>Save</code>.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Public subnet settings changed successfully!}}$$ </h2>

   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/f5e0c368-41a2-4239-bbe6-dea2461abe68"> </p>

   <p> Now let´s create a private subnet, which is for resources that will remain isolated from the internet.
   <p>- 17 - Choose <code>Creat subnet</code>, and then configure the following: .</p>
<ul style="list-style-type:square">
    <li><code>VPC ID</code>: select Lab VPC from the dropdown menu.</li>
    <li><code>Subnet name</code>: enter Private Subnet.</li>
    <li><code>Availability Zone</code>: select the first Availability Zone in the list. (Do not choose No Preference.)</li>
    <li><code>IPV4 CIDR</code> block: enter 10.0.0.0/23.</li>
</ul>
   <p>- 18 - Choose <code>Create subnet</code>.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Private subnet created successfully!}}$$ </h2>
   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/5796eda4-6071-4432-af4d-ebe3cee48472"> </p>

   <p>- 19 - Verify the state of the private subnet created.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Public Subnet available!}}$$ </h2>

   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/b3b5824f-5159-4ef9-8f2e-f7c38bc888a2"> </p>

   <p>Now my VPC has two subnets. However, these subnets are isolated and cannot communicate with resources outside the VPC. Next, I will configure the public subnet to connect to the internet through an interna gateway.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Congratulations! I have successfully created a public and a private subnet in the VPC.}}$$ </h2>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 3. Create an internet gateway}}$$<a id='3'></a></h1>
<p align="center">In this task, I will create an internet gateway so that internet traffic can access the public subnet. To grant access to or from the internet for instances in a subnet in a VPC, I will create an internet gateway and attach it to my VPC. Then I will add a route to my subnet´s route table that directs internet-bound traffic to the internet gate. </p><br>
<p align="center">Learn more: An internet gateway serves two purposes: To provide a target in your VPC route tables for internet-bound traffic, and to perform network address translation (NAT) for instances that have been assigned public IPv4 addres. </p>

   <p>- 20 - In the left naviagetion pane, choose <code>Internet gateways</code>.</p>
   <p>- 21 - Choose <code>Create Internet gateway</code> and configure the following:</p>
<ul style="list-style-type:square">
    <li><code>Name Tag</code>: senter Lab IGW.</li>
</ul>
   <p>- 22 - Choose <code>Create Internet gateway</code>.</p>

<h2 align="center"> $$\textcolor{white}{\textnormal{Internet gateway was created successfully!}}$$ </h2>
<p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/94ad9bbe-1828-42ad-b007-4cfb92a6ebc0"> </p>

   <p>- 23 - From the same page, choose <code>Actions</code> and choose <code>Attach to VPC</code>.</p>
   <p>- 24 - For <code>Available VPs</code>, select the <code>VPC</code> created from the dropdown menu.</p>
   <p>- 25 - Choose <code>Attach Internet gateway</code>.</p>

<h2 align="center"> $$\textcolor{white}{\textnormal{Internet gateway successfully attached to VPC!}}$$ </h2>
<p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/9b01203c-fa4c-4e63-a8c6-850a07f91b78"> </p>

   <p>- 26 - Verify Internet gateway state.</p>
   
   <h2 align="center"> $$\textcolor{white}{\textnormal{Internet gateway state is attached!}}$$ </h2>

   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/142bb5c3-5b6a-4e92-9643-d909582e2dfa"> </p>
   <p align="center">The internet gateway is now attached to your Lab VPC. Even though you have created an internet gateway and attached it to your VPC, you must also configure the route table of the public subnet to use the internet gate </p><br>

  <h2 align="center"> $$\textcolor{white}{\textnormal{Congratulations! I have successfully createdted an internet gateway so that internet traffic can access the public subnet.}}$$ </h2>

<h1 align="center"> $$\textcolor{orange}{\textnormal{Task 4. Routing intern traffic in the public subnet to the Internet gateway}}$$<a id='4'></a></h1>
<p align="center">In this task, I will create a route table and add a route to the route table to direct internet-bound traffic to my internet gateway and associate my public subnets with my route table. Each subnet in my VPC must be associated with a route table; the table controls the routing for the subnet. A subnet can only be associated with one route table at a time, but you can associate multiple subnets with the same route table.</p>
<p align="center"> Learn more: A route table contains a set of rules, called routes, that are used to determine where network traffic is directed. To use an internet gateway, your subnet´s route table must contain a route that directs internet-bound traffic to the internet gateway. You can scope the route to all destinations not explicitly known to the route table (0.0.0.0/0 for IPv4 or ::/0 for IPv6), or you can scope the route to a narrower range of IP addresses. If your subnet is associated with a route table that has a route to an internet gateway, it&apos;s known as a publi</p>

   <p>- 27 - In the left navigation pane, choose <code>Route Tables</code>.</p>
   <p>- 28 - Choose <code>Create Route Table</code>, and then configure the following:</p>
<ul style="list-style-type:square">
    <li><code>Name Optional</code>: enter Public Route Table.</li>
    <li><code>VPC</code>: select <code>VPC</code> from the dropdown menu.</li>
</ul>
   <p>- 29 - Choose <code>Create Route Table</code>.</p>   
   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/b6675178-3388-4847-b063-65cd9b0b72e9"> </p>
   
   <p>- 30 - Choose the <code>Routes</code> tab in the lower half of the page.</p>
   <p>- 31 - Choose <code>Edit Routes</code>.</p>
   <p>- 32 - Choose <code>Add route</code> and then configure the following:</p>
<ul style="list-style-type:square">
    <li><code>Destination</code>: enter 0.0.0.0/0.</li>
    <li><code>Target</code>: choose <code>Internet gteway</code> in the dropdown menu, and then choose the displayed Internet gateway ID.</li>
</ul>
   <p>- 33 - Choose <code>Save changes</code>.</p>

   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/61189c8c-b116-4267-9b57-7a0a0b948290"> </p>

   <p>- 34 - Choose <code>Subnet associations</code> tab.</p>
   <p>- 35 - Choose <code>Edit subnet associations</code>.</p>
   <p>- 36 - Select <code>Public Subnet</code> tab.</p>
   <p>- 37 - Choose <code>Save Associations</code>.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Congratulations! I have successfully updated subnet associations for Public Route Table!}}$$ </h2>
   <p align="center">  <img width="1000px" src="https://github.com/user-attachments/assets/e3b7e021-0d8a-4e35-83d4-0b3b22024a2a"> </p>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 5. Creating a public security group}}$$<a id='5'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 6. Lauching an Amazon EC2 instance into a public subnet}}$$<a id='6'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 7. Connecting to a public instance through HTTP}}$$<a id='7'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 8. Connecting to the Amazon EC2 instance in the public subnet through Session Manager}}$$<a id='8'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 9. Creating a NAT gateway and configuring routing in the private subnet}}$$<a id='9'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 10. Creating a security group for private resources}}$$<a id='10'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 11. Launching an Amazon EC2 instance into a private subnet}}$$<a id='11'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 12. Connecting to the Amazon EC2 instance in the private subnet}}$$<a id='12'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 13. Testing connectivity to the private instance from the public intance}}$$<a id='13'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 14. Retrieving instance metadata}}$$<a id='14'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Task 15. Understanding the basic of IPv6 networking on AWS}}$$<a id='15'></a></h1>

   <h1 align="center"> $$\textcolor{orange}{\textnormal{Conclusion}}$$<a id='16'></a></h1>
