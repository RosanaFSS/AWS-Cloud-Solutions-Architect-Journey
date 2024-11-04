<h3>AWS Hands-on, Securing Amazon S3 VPC Endpoint Communications</h3>
<p>November 4, 2024<br></p>


<p>Hey there, fellow lifelong learner! I´m <a href="https://www.linkedin.com/in/rosanafssantos/">Rosana</a>, and I’m genuinely excited to join you on this adventure.</p>
<p>It´s key part of my AWS hands-on journey.</p>
<p>Let´s get started!!</p>



<h2>Objective</h2>
<p>In this tutorial, we will:
<ul style="list-style-type:square">
    <li>Understand private and public subnets and why they can or cannot communicate with Amazon S3.</li>
    <li>Configure VPC endpoints using the AWS Management Console and AWS Command Line Interface (AWS CLI)</li>
    <li>Interact with Amazon S3 through a VPC endpoint in a private subnet. /li>
    <li>Create a VPC endpoint policy to restrict resource access.</li>
</ul></p>


<p>In this task, we will create a new Amazon VPC in the AWS Cloud. </p>
<p>With <code>Amazon VPC</code>, you can provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address ranges, creation of subnets, and configuration of route tables and network gateways. You can also use the enhanced security options in Amazon VPC to provide more granular access to and from the Amazon EC2 instances in your virtual network.</p>

<p align="center">  <img width="400px" src="https://github.com/user-attachments/assets/26915386-9a84-43b2-bb2f-597b90f6f3bc"> </p>

<p>1. At the top of the <code>AWS Managememt Console</code>, in the search bar, search for and choose <cpde>VPC</cpde>.</p>
   2. In the left navigation pane, choose Your VPCs</code>.</p>
   3. Choose Create VPC and configure the following:</p>
<ul style="list-style-type:square">
    <li>Resources to create: Choose  VPC only.</li>
    <li>Name tag - optional: Enter Lab VPC.</li>
    <li>Pv4 CIDR: Enter 10.0.0.0/16./li>
</ul>
   4. Choose <code>Create VPC</code>.</p>

<p align="center">  <img width="800px" src="https://github.com/user-attachments/assets/3a3eeffe-25de-4182-ae7a-902c6b6ec910"> </p>




