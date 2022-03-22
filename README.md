#!/bin/bash
sudo yum install python2 -y
sudo dnf install -y https://s3.us-east-1.amazonaws.com/amazon-ssm-us-east-1/latest/linux_amd64/amazon-ssm-agent.rpm
sudo su -
mkdir opt
cd opt
mkdir midserver
cd midserver/
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
yum install zip unzip -y
unzip awscliv2.zip
sudo ./aws/install
aws s3 cp s3://midserver/midserver_zipfile/mid-linux-installer.rome-06-23-2021__patch7-02-09-2022_02-23-2022_0935.linux.x86-64.rpm mid-linux-installer.rome-06-23-2021__patch7-02-09-2022_02-23-2022_0935.linux.x86-64.rpm
rpm -i mid-linux-installer.rome-06-23-2021__patch7-02-09-2022_02-23-2022_0935.linux.x86-64.rpm
