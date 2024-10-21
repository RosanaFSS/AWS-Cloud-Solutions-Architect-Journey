<h3>PROZ AWS Arquitet@s Program</h3>
<h1> Using the <code>AWS CLI</code> installed on Windows, I created a <strong><em>VPC</em></strong> that includes both a <strong><em>public and private subnet</em></strong> within the same Availability Zone, attached an <strong><em>Internet Gateway</em></strong>, and configured the <strong><em>Route Table</em></strong>.</h1>
<p>October 21, 2024<br></p><br>

<p>This highlighted in green is the architecture that I created.</p>
<p>Soon the architecture will be inserted here.</p>

<p></p>
<p>First I configured the <strong><em>Region</em></strong> as <code>sa-east-1</code>.</p>
<pre><code>aws configure list</code></pre>

<p></p>
<p>I confirmed the configration, especially the Region running the following command line.</p>
<pre><code>aws configure set region sa-east-1</code></pre>

<p>I recived the following output, what confirm that the Region is correct.</p>
<pre><code>                   
      Name                    Value             Type        Location
      ----                    -----             ----        --------
   profile                <not set>             None        None
access_key     **********[REDACTED] shared-credentials-file
secret_key     **********[REDACTED] shared-credentials-file
    region                sa-east-1       config-file        ~/.aws/config </code></pre>

<p></p>
<p>Then I created my <strong><em>VPC</em></strong> running the following command line
<pre><code> aws ec2 create-vpc --cidr-block 172.20.0.0/16 </code></pre>

The breakdown of the <strong><em>VPC</em></strong> I created is following</p>

<pre><code>
{
    "Vpc": {
        "CidrBlock": "172.20.0.0/16",
        "DhcpOptionsId": "dopt-0c13202cb9899edc4",
        "State": "pending",
        "VpcId": "vpc-0ebf8715637e2e32a",
        "OwnerId": "712107929769",
        "InstanceTenancy": "default",
        "Ipv6CidrBlockAssociationSet": [],
        "CidrBlockAssociationSet": [
            {
                "AssociationId": "vpc-cidr-assoc-05930ea08c6fb0097",
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

<p>And here I explain what means what part of the output.</p>
<ul>
    <li>CidrBlock: "172.20.0.0/16" shows that the VPC was created with the correct CIDR block you specified.</li>
    <li>DhcpOptionsId: This is the ID of the DHCP options set associated with the VPC.</li>
    <li>State: "pending" means the VPC creation is in progress. It generally transitions to "available" shortly after creation.</li>
    <li>VpcId: "vpc-00590e188b434d1fb" is the unique identifier for your new VPC. You'll use this ID for further configurations and operations.</li>
    <li>OwnerId: This indicates the AWS account owner of the VPC.</li>
    <li>InstanceTenancy: "default" means instances launched in the VPC will have the default tenancy.</li>
    <li>CidrBlockAssociationSet: Shows the CIDR block association details, confirming that the CIDR block is successfully associated with your VPC.</li>
</ul>

<p><br>
Next a defined a specific <strong><em>name for my VPC</em></strong>.</p>
<pre><code> aws ec2 create-tags --resources vpc-00590e188b434d1fb --tags Key=Name,Value=vpc-rosana-santos-proz </code></pre>

![image](https://github.com/user-attachments/assets/7fc040b5-da14-4086-a981-cde81802113d)

<p></p>
<p>I created a <strong><em>Public Subnet</em></strong> .</p>
<pre><code> aws ec2 create-subnet --vpc-id vpc-0ebf8715637e2e32a --cidr-block 172.20.2.0/24 --availability-zone sa-east-1a </code></pre>
<p>My output was the following</p>
<pre><code>
{
    "Subnet": {
        "AvailabilityZone": "sa-east-1a",
        "AvailabilityZoneId": "sae1-az1",
        "AvailableIpAddressCount": 251,
        "CidrBlock": "172.20.2.0/24",
        "DefaultForAz": false,
        "MapPublicIpOnLaunch": false,
        "State": "available",
        "SubnetId": "subnet-044776b45f04504d0",
        "VpcId": "vpc-0ebf8715637e2e32a",
        "OwnerId": "712107929769",
        "AssignIpv6AddressOnCreation": false,
        "Ipv6CidrBlockAssociationSet": [],
        "SubnetArn": "arn:aws:ec2:sa-east-1:712107929769:subnet/subnet-044776b45f04504d0",
        "EnableDns64": false,
        "Ipv6Native": false,
        "PrivateDnsNameOptionsOnLaunch": {
            "HostnameType": "ip-name",
            "EnableResourceNameDnsARecord": false,
            "EnableResourceNameDnsAAAARecord": false
        }
    }
</code></pre>

![image](https://github.com/user-attachments/assets/de292524-0513-4461-a486-012e38584fad)


<p>I created a <strong><em>Private Subnet</em></strong> .</p>


