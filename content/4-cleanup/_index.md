+++
title = "Clean up resources"
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

You would clean up resources in the following order:

#### Delete S3 bucket

1. Go to [the management interface of the S3 service](https://s3.console.aws.amazon.com/s3/home?region=ap-southeast-1&region=ap-southeast-1)
  + Click on S3 bucket **s3-instancerole-001**.
  + Click **Empty**.

![Role](/images/role/c01.png?featherlight=false&width=90pc)

2. Enter **permanently delete** to confirm, then click **Empty** to delete all data in S3 bucket.
  + Click **Exit** to return to the S3 interface.

3. Click the S3 bucket **s3-instancerole-001** , then click **Delete**.
 
![Role](/images/role/c02.png?featherlight=false&width=90pc)

4. Enter the bucket name then click **Delete bucket** to delete the S3 bucket.

#### Delete EC2 Instance

1. Go to [EC2 service management interface](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#Instances:)
  + Click on the Instance we created for the lab.
  + Click **Instance state**.
  + Click **Terminate instance** , then click **Terminate** to confirm.
 
  ![Role](/images/role/c03.png?featherlight=false&width=90pc)

2. Go to [IAM service management interface](https://console.aws.amazon.com/iamv2/home#/users)
  + Click **Users**
  + Click on user **iamaccesskey**.
  + Click **Delete**. Enter the username **iamaccesskey** and click **Delete**.

![Role](/images/role/c04.png?featherlight=false&width=90pc)

3. Click **Roles**.
  + Enter **ec2** to find the role we created.
  + Click on role **ec2roles3upload**.
  + Click **Delete**. Enter the role name **ec2roles3upload** and click **Delete** to delete the IAM Role.

![Role](/images/role/c05.png?featherlight=false&width=90pc)