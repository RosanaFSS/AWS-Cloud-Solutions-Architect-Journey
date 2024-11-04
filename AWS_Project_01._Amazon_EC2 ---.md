<h3>AWS Hands-on, Securing Amazon S3 VPC Endpoint Communications</h3>
<p>November 4, 2024<br></p>


<p>Hey there, fellow lifelong learner! I´m <a href="https://www.linkedin.com/in/rosanafssantos/">Rosana</a>, and I’m genuinely excited to join you on this adventure. It´s key part of my AWS hands-on journey. Let´s get started!!</p>

<h1 align="center"> $$\textcolor{white}{\textnormal{Objectives}}$$ </h1>
<p align="center"> After completing this lab, you should know how to do the following:</p>
<ul style="list-style-type:square">
    <li>Create an Amazon VPC.</li>
    <li>Create public and private subnets.<li>
    <li>Create an internet gateway.</li>
    <li>Configure a route table and associate it to a subnet.</li>
    <li>Create an Amazon Elastic Compute Cloud (Amazon EC2) instance and make the instance publicly accessible.</li>
    <li>Isolate an Amazon EC2 instance in a private subnet.</li>
    <li>Isolate an Amazon EC2 instance in a private subnet.</li>
    <li>Connect to Amazon EC2 instances using Session Manager, a capability of AWS Systems Manager.</li>
</ul></p>

<p align="center">In this task, we will create a new Amazon VPC in the AWS Cloud. </p>

<p align="center">With <code>Amazon VPC</code>, you can provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address ranges, creation of subnets, and configuration of route tables and network gateways. You can also use the enhanced security options in Amazon VPC to provide more granular access to and from the Amazon EC2 instances in your virtual network.</p>

<p align="center">  <img width="400px" src="https://github.com/user-attachments/assets/e9d234c8-4458-46ae-9a5a-765fd31701cc"> </p>

<p>1. At the top of the <code>AWS Managememt Console</code>, in the search bar, search for and choose <code>VPC</code>.</p>
   2. In the left navigation pane, choose <code>Your VPCs</code>.</p>
   3. Choose <code>Create VPC</code> and configure the following:</p>
<ul style="list-style-type:square">
    <li>Resources to create: Choose  VPC only.</li>
    <li>Name tag - optional: Enter Lab VPC.</li>
    <li>Pv4 CIDR: Enter 10.0.0.0/16./li>
</ul>
   4. Choose <code>Create VPC</code>.</p>

<h1 align="center"> $$\textcolor{white}{\textnormal{VPC created.}}$$ </h1>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/3a3eeffe-25de-4182-ae7a-902c6b6ec910"> </p><br>

   <p>5. Verify the state of the <code>VPC</code> created.</p>

   <h1 align="center"> $$\textcolor{white}{\textnormal{VPC is available.}}$$ </h1>

<p align="center">  <img width="400px" src="https://github.com/user-attachments/assets/b2a54727-ea73-4aba-9042-73e593955e08"> </p>

   <p>6. From the same page, choose <code>Actions</code>code> and choose <code>Edit VPC SettingsVPC</code>.</p>
   <p>7. From the <code>DNS settings</code> section, select <code>Enable DNS hostnames</code>.</p>
   <p>8. Choose <code>Save</code>.</p>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/103bfb20-842b-4977-80c0-69ac3ab34fef"> </p><br>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/d9f72f65-af6f-4092-a540-6c68b0114e17"> </p>

<h1 align="center"> $$\textcolor{white}{\textnormal{VPC settings modified successfully.}}$$ </h1>







