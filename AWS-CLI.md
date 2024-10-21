<h3>PROZ AWS Arquitet@s Program</h3>
<h1> Using the <code>AWS CLI</code> installed on Windows, I created a <strong><em>VPC</em></strong> that includes both a <strong><em>public and private subnet</em></strong> within the same Availability Zone, attached an <strong><em>Internet Gateway</em></strong>, and configured the <strong><em>Route Table</em></strong>.</h1>
<p>October 21, 2024<br></p><br>

<p>This highlighted in green is the architecture that I created.</p>

<p></p>
<p>First I configred the <strong><em>Region</em></strong> as sa-east-1.
<pre><code></p>C:\Windows\System32>aws configure set region sa-east-1</code></pre>

<p></p>
<p>I started creating a <strong><em>VPC</em></strong> .</p>

<p>After running the following command line
<pre><code> aws ec2 create-vpc --cidr-block 172.20.0.0/16 </code></pre>

my <strong><em>VPC</em></strong> was created.</p>

<pre><code>
{
    "Vpc": {
        "CidrBlock": "172.20.0.0/16",
        "DhcpOptionsId": "dopt-00b416862a2f77fb1",
        "State": "pending",
        "VpcId": "vpc-00590e188b434d1fb",
        "OwnerId": "712107929769",
        "InstanceTenancy": "default",
        "Ipv6CidrBlockAssociationSet": [],
        "CidrBlockAssociationSet": [
            {
                "AssociationId": "vpc-cidr-assoc-0ec9980bc043c81b5",
                "CidrBlock": "172.20.0.0/16",
                "CidrBlockState": {
                    "State": "associated"
                }
            }
        ],
        "IsDefault": false
    }
}
</code></pre>

<p>Here is the breakdown of each part of my output.</p>
<ul>
    <li>CidrBlock: "172.20.0.0/16" shows that the VPC was created with the correct CIDR block you specified.</li>
    <li>DhcpOptionsId: This is the ID of the DHCP options set associated with the VPC.</li>
    <li>State: "pending" means the VPC creation is in progress. It generally transitions to "available" shortly after creation.</li>
    <li>VpcId: "vpc-00590e188b434d1fb" is the unique identifier for your new VPC. You'll use this ID for further configurations and operations.</li>
    <li>OwnerId: This indicates the AWS account owner of the VPC.</li>
    <li>InstanceTenancy: "default" means instances launched in the VPC will have the default tenancy.</li>
    <li>CidrBlockAssociationSet: Shows the CIDR block association details, confirming that the CIDR block is successfully associated with your VPC.</li>
</ul>

<p>I defined a specific <strong><em>name for my VPC</em></strong> .</p>
<pre><code> aws ec2 create-tags --resources vpc-00590e188b434d1fb --tags Key=Name,Value=vpc-rosana-santos-proz </code></pre>

![image](https://github.com/user-attachments/assets/7fc040b5-da14-4086-a981-cde81802113d)

<p></p>
<p>I created a <strong><em>Public Subnet</em></strong> .</p>


<p>I created a <strong><em>Private Subnet</em></strong> .</p>


