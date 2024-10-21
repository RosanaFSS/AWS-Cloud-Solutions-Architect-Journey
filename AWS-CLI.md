<h3>PROZ AWS Arquitet@s Program</h3>
<h1> Using the <code>AWS CLI</code> installed on Windows, I created a <strong><em>VPC</em></strong> that includes both a <strong><em>public and private subnet</em></strong> within the same Availability Zone, attached an <strong><em>Internet Gateway</em></strong>, and configured the <strong><em>Route Table</em></strong>.</h1>
<p>October 21, 2024<br></p><br>

<p>This highlighted in green is the architecture that I created.</p>
<p>Soon the architecture will be inserted here.</p>

<h2>Configured Region</h2>
<p>First I configured the <strong><em>Region</em></strong> as <code>sa-east-1</code>.</p>
<pre><code>aws configure set region sa-east-1</code></pre>

<h2>Checked Region</h2>
<p>I confirmed the configuration, especially the Region running the following command line.</p>
<pre><code>aws configure list</code></pre>

<p>I received the following output, what confirm that the Region is correct.</p>
<pre><code>                   
      Name                    Value             Type        Location
      ----                    -----             ----        --------
   profile                <not set>             None        None
access_key     **********[REDACTED] shared-credentials-file
secret_key     **********[REDACTED] shared-credentials-file
    region                sa-east-1       config-file        ~/.aws/config </code></pre>

<h2>Created VPC</h2>
<p>Then I created my <strong><em>VPC</em></strong> running the following command line</p>
<pre><code> aws ec2 create-vpc --cidr-block 172.20.0.0/16 </code></pre>

The breakdown of the <strong><em>VPC</em></strong> I created is following</p>
<pre><code>
{
    "Vpc": {
        "CidrBlock": "172.20.0.0/16",
        "DhcpOptionsId": "dopt-0c13202cb9899edc4",
        "State": "pending",
        "VpcId": "vpc-0e33f5da409fa3d35",
        "OwnerId": "712107929769",
        "InstanceTenancy": "default",
        "Ipv6CidrBlockAssociationSet": [],
        "CidrBlockAssociationSet": [
            {
                "AssociationId": "vpc-cidr-assoc-0159884409164b213",
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

<h2>Customized VPC name</h2>
<p>Next I defined a specific <strong><em>name for my VPC</em></strong>.</p>
<pre><code> aws ec2 create-tags --resources vpc-00590e188b434d1fb --tags Key=Name,Value=vpc-rosana-santos-proz </code></pre>

![image](https://github.com/user-attachments/assets/7fc040b5-da14-4086-a981-cde81802113d)

<h2>Created a Security Group</h2>
<pre><code>aws ec2 create-security-group --group-name rosana-santos-proz --description "Security Group for my PROZ Arquitet@s Program app" --vpc-id vpc-0e33f5da409fa3d35</code></pre>

The output of the <strong><em>Security Group</em></strong> created is the following</p>
<pre><code>
{
    "GroupId": "sg-048adbbb7cda6e319"
}
</code></pre>

<h2>Configured Inbound Rules for the Security Group</h2>
<h4>Allowed SSH traffic (port 22) from any IP</h4>
<pre><code>aws ec2 authorize-security-group-ingress --group-id sg-048adbbb7cda6e319 --protocol tcp --port 22 --cidr 0.0.0.0/0</code></pre>
<pre><code>
{
    "Return": true,
    "SecurityGroupRules": [
        {
            "SecurityGroupRuleId": "sgr-09a89823013ce769c",
            "GroupId": "sg-048adbbb7cda6e319",
            "GroupOwnerId": "712107929769",
            "IsEgress": false,
            "IpProtocol": "tcp",
            "FromPort": 22,
            "ToPort": 22,
            "CidrIpv4": "0.0.0.0/0"
        }
    ]
}
</code></pre>


<h4>Allowed HTTP traffic (port 80) from any IP</h4>
<pre><code>aaws ec2 authorize-security-group-ingress --group-id sg-048adbbb7cda6e319 --protocol tcp --port 80 --cidr 0.0.0.0/0</code></pre>
<pre><code>
{
    "Return": true,
    "SecurityGroupRules": [
        {
            "SecurityGroupRuleId": "sgr-02829d929e511c35b",
            "GroupId": "sg-048adbbb7cda6e319",
            "GroupOwnerId": "712107929769",
            "IsEgress": false,
            "IpProtocol": "tcp",
            "FromPort": 80,
            "ToPort": 80,
            "CidrIpv4": "0.0.0.0/0"
        }
    ]
}
</code></pre>

<h2>Outbound rules for Security Group</h2>
<p>Security groups by default allo all outbound traffic, ensuring that instances can initiate requests to the internet or other AWS services.<br>
There’s typically no need to set specific outbound rules unless you have particular restrictions or security policies in place. </p>

<h2>Created Private Subnet</h2>
<p></p>
<p>I created a <strong><em>Private Subnet</em></strong> running the following command line</p>
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
        "SubnetId": "subnet-00f8fe1d4c1787048",
        "VpcId": "vpc-0e33f5da409fa3d35",
        "OwnerId": "712107929769",
        "AssignIpv6AddressOnCreation": false,
        "Ipv6CidrBlockAssociationSet": [],
        "SubnetArn": "arn:aws:ec2:sa-east-1:712107929769:subnet/subnet-00f8fe1d4c1787048",
        "EnableDns64": false,
        "Ipv6Native": false,
        "PrivateDnsNameOptionsOnLaunch": {
            "HostnameType": "ip-name",
            "EnableResourceNameDnsARecord": false,
            "EnableResourceNameDnsAAAARecord": false
        }
    }
}
</code></pre>

![image](https://github.com/user-attachments/assets/284722c3-84ff-4d93-b1f7-12a0266a9f8f)

<p></p>
<p>I defined a specifc name for this <strong><em>Public Subnet</em></strong> .</p>
<pre><code> aws ec2 create-tags --resources subnet-00f8fe1d4c1787048 --tags Key=Name,Value=private-subnet-rosana-santos-proz </code></pre>

![image](https://github.com/user-attachments/assets/8ae04818-0e38-4f69-87ef-7a1a2d8d4609)

<h2>Created Public Subnet</h2>
<p>I created a <strong><em>Public Subnet</em></strong> running the following command line, and this time I´m already defining its customized name.</p>
<pre><code> aws ec2 create-subnet --vpc-id vpc-0e33f5da409fa3d35 --cidr-block 172.20.16.0/24 --availability-zone sa-east-1a --tag-specifications "ResourceType=subnet,Tags=[{Key=Name,Value=public-subnet-rosana-santos-proz}]"</code></pre>
<p>My output was the following</p>
<pre><code>
{
    "Subnet": {
        "AvailabilityZone": "sa-east-1a",
        "AvailabilityZoneId": "sae1-az1",
        "AvailableIpAddressCount": 251,
        "CidrBlock": "172.20.16.0/24",
        "DefaultForAz": false,
        "MapPublicIpOnLaunch": false,
        "State": "available",
        "SubnetId": "subnet-06275e0cf1c1039ae",
        "VpcId": "vpc-0e33f5da409fa3d35",
        "OwnerId": "712107929769",
        "AssignIpv6AddressOnCreation": false,
        "Ipv6CidrBlockAssociationSet": [],
        "Tags": [
            {
                "Key": "Name",
                "Value": "public-subnet-rosana-santos-proz"
            }
        ],
        "SubnetArn": "arn:aws:ec2:sa-east-1:712107929769:subnet/subnet-06275e0cf1c1039ae",
        "EnableDns64": false,
        "Ipv6Native": false,
        "PrivateDnsNameOptionsOnLaunch": {
            "HostnameType": "ip-name",
            "EnableResourceNameDnsARecord": false,
            "EnableResourceNameDnsAAAARecord": false
        }
    }
}
</code></pre>

![image](https://github.com/user-attachments/assets/28ae79d7-188d-46ba-b450-d5fd2c05f8d0)

<h2>Created an Internet Gateway</h2>
<p></p>
<p>I created an <strong><em>Internet Gateway</em></strong> running the following command line</p>
<pre><code>aws ec2 create-internet-gateway</code></pre>
<p>My output was the following</p>
<pre><code>
{
    "InternetGateway": {
        "Attachments": [],
        "InternetGatewayId": "igw-0ce6321c099d8c5e2",
        "OwnerId": "712107929769",
        "Tags": []
    }
}      
</code></pre>

<p>I customized the Internet Gateway name</p>
<pre><code>aws ec2 create-tags --resources igw-0ce6321c099d8c5e2 --tags Key=Name,Value=internet-gateway-rosana-santos-proz</code></pre>
<p>There was no output</p>

<h2>Attached the Internet Gateway to the VPC</h2>
<p></p>
<p>I attached the <strong><em>Internet Gateway</em></strong> to the <strong><em>VPC</em></strong>, enabling internet access for resources in my public subnets.</p>
<pre><code>aws ec2 attach-internet-gateway --internet-gateway-id igw-0ce6321c099d8c5e2 --vpc-id vpc-0e33f5da409fa3d35<vpc-id></code></pre>
<p>There was no output</p>

<h2>Checked if Internet Gateway is attached to the VPC</h2>
<pre><code>aws ec2 describe-internet-gateways --internet-gateway-ids igw-0ce6321c099d8c5e2</code></pre>
<p>By inspecting my output the Internet Gateway is successfully attached to your VPC. </p>
<pre><code>
{
    "InternetGateways": [
        {
            "Attachments": [
                {
                    "State": "available",
                    "VpcId": "vpc-0e33f5da409fa3d35"
                }
            ],
            "InternetGatewayId": "igw-0ce6321c099d8c5e2",
            "OwnerId": "712107929769",
            "Tags": [
                {
                    "Key": "Name",
                    "Value": "internet-gateway-rosana-santos-proz"
                }
            ]
        }
    ]
}    
</code></pre>

![image](https://github.com/user-attachments/assets/f32d23c8-c55f-4309-bab3-3888b0055f30)


<h2>Created Route Tables</h2>
<h4>One for the Public subnet and the other for the Private subnet</h4>
<p>I created two <strong><em>Route Tables</em></strong>.<br><br>
I create the first one.</p>
<pre><code>aws ec2 create-route-table --vpc-id vpc-0e33f5da409fa3d35</code></pre>
<p>The output indicates that the route table was successfully created</p>
<pre><code>
{
    "RouteTable": {
        "Associations": [],
        "PropagatingVgws": [],
        "RouteTableId": "rtb-0b080c0655ebaf781",
        "Routes": [
            {
                "DestinationCidrBlock": "172.20.0.0/16",
                "GatewayId": "local",
                "Origin": "CreateRouteTable",
                "State": "active"
            }
        ],
        "Tags": [],
        "VpcId": "vpc-0e33f5da409fa3d35",
        "OwnerId": "712107929769"
    },
    "ClientToken": "b42fce45-3914-4fff-993e-4d52af0a5bcf"
}
</code></pre>

<p>I create the second one.</p>
<pre><code>aws ec2 create-route-table --vpc-id vpc-0e33f5da409fa3d35</code></pre>
<p>The output indicates that the route table was successfully created</p>
<pre><code>
{
    "RouteTable": {
        "Associations": [],
        "PropagatingVgws": [],
        "RouteTableId": "rtb-00b25531b4f76f886",
        "Routes": [
            {
                "DestinationCidrBlock": "172.20.0.0/16",
                "GatewayId": "local",
                "Origin": "CreateRouteTable",
                "State": "active"
            }
        ],
        "Tags": [],
        "VpcId": "vpc-0e33f5da409fa3d35",
        "OwnerId": "712107929769"
    },
    "ClientToken": "026a6185-e103-4326-a3e1-1299c1b7c1cf"
}
</code></pre>

<h2>Associate Route Tables with Subnets</h2>
<h4>Associated the Public Route Table to the Public Subnet</h4>
<pre><code>aws ec2 associate-route-table --route-table-id rtb-0b080c0655ebaf781 --subnet-id subnet-06275e0cf1c1039ae</code></pre>

![image](https://github.com/user-attachments/assets/b649caa5-6f65-49b7-a19d-21b83cbf170f)

<h4>Associated the Private Route Table to the Private Subnet</h4>
<pre><code>aws ec2 associate-route-table --route-table-id rtb-00b25531b4f76f886 --subnet-id subnet-00f8fe1d4c1787048</code></pre>

![image](https://github.com/user-attachments/assets/d92b8518-0276-4043-b45e-95d336b4a5cf)



<h2>Associated the Subnets to its own Route Table</h2>
<pre><code>aws ec2 associate-route-table --route-table-id rtb-0b080c0655ebaf781 --subnet-id subnet-06275e0cf1c1039ae</code></pre>

<h2>Cheked the Architecure</h2>
<pre><code>aws ec2 describe-vpcs
aws ec2 describe-subnets
aws ec2 describe-internet-gateways
aws ec2 describe-route-tables
</code></pre>
