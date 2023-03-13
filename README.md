# Basic Lab - Web Application with AWS CloudFormation
This lab is aimed at developing basic and beginning skills in AWS CloudFormation.
I provide the CloudFormation template in JSON for creating all lab resources.

# AWS CloudFormation Template
WebApp-CloudFormation.json

# Architecture
![alt text](https://github.com/Henreis90/Lab01-CloudFormationJson/blob/main/Lab-AWS-01.drawio.png)

[Lab-AWS-01.drawio.png](https://github.com/Henreis90/Lab01-CloudFormationJson/blob/main/Lab-AWS-01.drawio.png)


# Resources created:

2 EC2 instances running the web application with Apache.

1 Application Load Balancer distributing traffic between the two instances.

1 Internet Gateway.

1 EC2 instance to use as a bastion.

3 Security Groups.

1 AWS CloudTrail trail for management logs.

1 S3 Bucket to store the logs.

1 pair of keys to connect to EC2 instances via SSH.

# Warning!
Before sending the template to deploy, change the "PublicKeyMaterial" field with a unique private key. Import this key into AWS before running the template. See the following example:

        "MyKeyPair": {
            "Type": "AWS::EC2::KeyPair",
            "Properties": {
                "KeyName": "mykeypair",
                "PublicKeyMaterial":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCedgSOwL5RrCk7v0q0OThH/2YmaOtFux+tMAsHflYU9dPKtXBaoTApgfkFo2P6QBMBQUO2df7UAsVPIfLOlckPR8dM4MBiW+L88lnwcXlDwbWJLihL5NCqfTkiId7ajKU6T8rP8hdP30p8VuBKQtCPeeXCgHoQNgiJlJYRwjrwv4OyqiKIivq3KuJQzr0hUn44horn+e7iClwSmpgh3PLvLUv+l+We/+ggzZmEavkH6ms8D9+tXu7KowcrGUVLi370GV3OcPYoRoPQ83t6Ge7LLOb6QpxyKwsRNQL7hUpLwmvfzCKyWWnCGqRG7q5pGBru+wKHw8gQKvF8y5rwEnYj rsa-key-20230227"
            }
        },


# Final test

To test the lab, look for the load balancer, copy the DNS name and paste it in the browser with internet access. If the message WebServer 1 or WebServer 2 appears and when you refresh the page a few times, it will go instantly. This is the load balancer working.
