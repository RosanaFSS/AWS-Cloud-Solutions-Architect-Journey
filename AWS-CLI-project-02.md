<h3>PROZ AWS Arquitet@s Program</h3>
<h1> Create a simple <code><em>EC2</em></code> instance.</h1>
<p>October 21, 2024<br></p><br>

<h2>Configured Region</h2>
<p>First I configured the <strong><em>Region</em></strong> as <code>sa-east-1</code>.</p>
<pre><code>aws configure set region sa-east-1</code></pre>

<h2>Checked Region</h2>


aws ec2 create-key-pair --key-name rosana-santos-keys --query 'KeyMaterial' --output text > rosana-santos-keys.pem

![image](https://github.com/user-attachments/assets/064bd82b-f4cf-42df-97ec-6e0b2ccb92d9)

he output indicates that your EC2 instance has been successfully created. Here are key details confirming the setup:

AMI: ami-0989c1b438266c944 (Amazon Linux 2023)
Instance Type: t2.micro
Key Pair: rosana-santos-keys
Security Group: rosana-santos-proz (sg-048adbbb7cda6e319), allowing HTTP and SSH as required.
Subnet: subnet-06275e0cf1c1039ae (Public subnet)
Tags: Name set to ec2-rosana-santos-proz
Block Device: Configured correctly as DeviceName=/dev/xvda
The instance state is initially "pending", which means it's in the process of launching. It should transition to "running" soon after.

C:\Windows\System32>aws ec2 run-instances --image-id ami-0989c1b438266c944 --count 1 --instance-type t2.micro --key-name rosana-santos-keys --security-group-ids sg-048adbbb7cda6e319 --subnet-id subnet-06275e0cf1c1039ae --associate-public-ip-address --block-device-mappings "[{\"DeviceName\":\"/dev/xvda\",\"Ebs\":{\"VolumeSize\":8,\"VolumeType\":\"gp3\"}}]" --tag-specifications "ResourceType=instance,Tags=[{Key=Name,Value=ec2-rosana-santos-proz}]"
{
    "Groups": [],
    "Instances": [
        {
            "AmiLaunchIndex": 0,
            "ImageId": "ami-0989c1b438266c944",
            "InstanceId": "i-05297d684c53e0c2c",
            "InstanceType": "t2.micro",
            "KeyName": "rosana-santos-keys",
            "LaunchTime": "2024-10-21T21:42:40+00:00",
            "Monitoring": {
                "State": "disabled"
            },
            "Placement": {
                "AvailabilityZone": "sa-east-1a",
                "GroupName": "",
                "Tenancy": "default"
            },
            "PrivateDnsName": "ip-172-20-16-86.sa-east-1.compute.internal",
            "PrivateIpAddress": "172.20.16.86",
            "ProductCodes": [],
            "PublicDnsName": "",
            "State": {
                "Code": 0,
                "Name": "pending"
            },
            "StateTransitionReason": "",
            "SubnetId": "subnet-06275e0cf1c1039ae",
            "VpcId": "vpc-0e33f5da409fa3d35",
            "Architecture": "x86_64",
            "BlockDeviceMappings": [],
            "ClientToken": "165cc2cb-444f-477b-9e82-7bccf4504e63",
            "EbsOptimized": false,
            "EnaSupport": true,
            "Hypervisor": "xen",
            "NetworkInterfaces": [
                {
                    "Attachment": {
                        "AttachTime": "2024-10-21T21:42:40+00:00",
                        "AttachmentId": "eni-attach-035ea0ef2d5f147c7",
                        "DeleteOnTermination": true,
                        "DeviceIndex": 0,
                        "Status": "attaching",
                        "NetworkCardIndex": 0
                    },
                    "Description": "",
                    "Groups": [
                        {
                            "GroupName": "rosana-santos-proz",
                            "GroupId": "sg-048adbbb7cda6e319"
                        }
                    ],
                    "Ipv6Addresses": [],
                    "MacAddress": "02:1f:a3:1c:ab:a5",
                    "NetworkInterfaceId": "eni-0852e13193e072b28",
                    "OwnerId": "712107929769",
                    "PrivateIpAddress": "172.20.16.86",
                    "PrivateIpAddresses": [
                        {
                            "Primary": true,
                            "PrivateIpAddress": "172.20.16.86"
                        }
                    ],
                    "SourceDestCheck": true,
                    "Status": "in-use",
                    "SubnetId": "subnet-06275e0cf1c1039ae",
                    "VpcId": "vpc-0e33f5da409fa3d35",
                    "InterfaceType": "interface"
                }
            ],
            "RootDeviceName": "/dev/xvda",
            "RootDeviceType": "ebs",
            "SecurityGroups": [
                {
                    "GroupName": "rosana-santos-proz",
                    "GroupId": "sg-048adbbb7cda6e319"
                }
            ],
            "SourceDestCheck": true,
            "StateReason": {
                "Code": "pending",
                "Message": "pending"
            },
            "Tags": [
                {
                    "Key": "Name",
                    "Value": "ec2-rosana-santos-proz"
                }
            ],
            "VirtualizationType": "hvm",
            "CpuOptions": {
                "CoreCount": 1,
                "ThreadsPerCore": 1
            },
            "CapacityReservationSpecification": {
                "CapacityReservationPreference": "open"
            },
            "MetadataOptions": {
                "State": "pending",
                "HttpTokens": "required",
                "HttpPutResponseHopLimit": 2,
                "HttpEndpoint": "enabled",
                "HttpProtocolIpv6": "disabled",
                "InstanceMetadataTags": "disabled"
            },
            "EnclaveOptions": {
                "Enabled": false
            },
            "BootMode": "uefi-preferred",
            "PrivateDnsNameOptions": {
                "HostnameType": "ip-name",
                "EnableResourceNameDnsARecord": false,
                "EnableResourceNameDnsAAAARecord": false
            },
            "MaintenanceOptions": {
                "AutoRecovery": "default"
            },
            "CurrentInstanceBootMode": "legacy-bios"
        }
    ],
    "OwnerId": "712107929769",
    "ReservationId": "r-05c58a5d49a76045c"
}


C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>
C:\Windows\System32>












































































