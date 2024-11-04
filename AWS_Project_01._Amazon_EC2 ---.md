<h3>AWS Hands-on</h3>
<p>November 4, 2024<br></p>


<p>Hey there, fellow lifelong learner! I´m <a href="https://www.linkedin.com/in/rosanafssantos/">Rosana</a>, and I’m genuinely excited to join you on this adventure. It´s key part of my AWS hands-on journey. Let´s get started!!</p>

<h1 align="center"> $$\textcolor{white}{\textnormal{Objectives}}$$ </h1>
<p align="center"> After completing this lab, you should know how to do the following:</p>
<ul style="list-style-type:square">
    <li>Create an Amazon VPC.</li>
    <li>Create public and private subnets.</li>
    <li>Create an internet gateway.</li>
    <li>Configure a route table and associate it to a subnet.</li>
    <li>Create an Amazon Elastic Compute Cloud (Amazon EC2) instance and make the instance publicly accessible.</li>
    <li>Isolate an Amazon EC2 instance in a private subnet.</li>
    <li>Isolate an Amazon EC2 instance in a private subnet.</li>
    <li>Connect to Amazon EC2 instances using Session Manager, a capability of AWS Systems Manager.</li>
</ul></p><br>

<h1 align="center"> $$\textcolor{orange}{\textnormal{Task 1. Create an Amazon VPC in a Region}}$$ </h1>
<p align="center">In this task, we will create a new Amazon VPC in the AWS Cloud. </p>

<p align="center">With <code>Amazon VPC</code>, you can provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address ranges, creation of subnets, and configuration of route tables and network gateways. You can also use the enhanced security options in Amazon VPC to provide more granular access to and from the Amazon EC2 instances in your virtual network.</p>

<p align="center">  <img width="200px" src="https://github.com/user-attachments/assets/e9d7e6cc-6dc6-4b9f-8fb8-3db3a670babe"> </p>

   <p>01. At the top of the <code>AWS Managememt Console</code>, in the search bar, search for and choose <code>VPC</code>.</p>
   <p>02. In the left navigation pane, choose <code>Your VPCs</code>.</p>
   <p>03. Choose <code>Create VPC</code> and configure the following:</p>
<ul style="list-style-type:square">
    <li>Resources to create: Choose  VPC only.</li>
    <li>Name tag - optional: Enter Lab VPC.</li>
    <li>Pv4 CIDR: Enter 10.0.0.0/16./li>
</ul>
   <p>04. Choose <code>Create VPC</code>.</p>

<h2 align="center"> $$\textcolor{white}{\textnormal{VPC is created.}}$$ </h2>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/3a3eeffe-25de-4182-ae7a-902c6b6ec910"> </p><br>

   <p>05. Verify the state of the <code>VPC</code> created.</p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{VPC is available.}}$$ </h2>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/b2a54727-ea73-4aba-9042-73e593955e08"> </p>

   <p>06. From the same page, choose <code>Actions</code>code> and choose <code>Edit VPC SettingsVPC</code>.</p>
   <p>07. From the <code>DNS settings</code> section, select <code>Enable DNS hostnames</code>.</p>
   <p>08. Choose <code>Save</code>.</p>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/103bfb20-842b-4977-80c0-69ac3ab34fef"> </p>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/d9f72f65-af6f-4092-a540-6c68b0114e17"> </p>

<h2 align="center"> $$\textcolor{white}{\textnormal{VPC settings modified successfully.}}$$ </h2>
<p align="center"> Any Amazon EC2 instances launched into this Amazon VPC now automatically receive a DNS hostname. You can also create a more meaningful DNS name (for example, app.company.com) using records in Amazon Route 53. </p><br>
<p align="center"> <p align="center"> Congratulations! You have successfully created your own VPC and now you can launch the AWS resources in this defined virtual network </p><br><br>

<h1 align="center"> $$\textcolor{orange}{\textnormal{Task 2. Create public and private subnets}}$$ </h1>
<p align="center">In this task, you create a public subnet and a private subnet in the lab VPC. To add a new subnet to your VPC, you must specify an IPv4 CIDR block for the subnet from the range of your VPC. You can specify the Availability Zone in which you want the subnet to reside. You can have multiple subnets in the same Availability Zone. </p>

<p align="center">  <img width="200px" src="https://github.com/user-attachments/assets/81b525d4-c4fc-43ee-9e1b-dacdea06c22c"> </p>

<p align="center">Note: A subnet is a sub-range of IP addresses within a network. You can launch AWS resources into a specified subnet. Use a public subnet for resources that must be connected to the internet, and use a private subnet for resources that are to remain isolated from the internet. </p>

   <p>09. In the left navigation pane, choose <code>Subnets</code>.</p>
   <p>10. Choose <code>Create subnet</code> and configure the following:</p>
<ul style="list-style-type:square">
    <li><code>VPC ID</code>: select Lab VPC from the dropdown menu.</li>
    <li><code>Subnet name</code>: enter Public Subnet.</li>
    <li><code>Availability Zone</code>: select the first Availability Zone in the list. (Do not choose No Preference.)</li>
    <li><code>IPV4 CIDR</code> block: enter 10.0.0.0/24</li>
</ul>
   <p>11. Choose <code>Create subnet</code>.</p>

   <p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/341fc24f-9d8c-404b-a2c2-33bcc087e277"> </p>

   <h2 align="center"> $$\textcolor{white}{\textnormal{Private subnet created successfully.}}$$ </h2>












