+++
title = "Create IAM role"
weight = 1
chapter = false
pre = "<b>3.1 </b>"
+++


#### Generate IAM user and access key

1. Go to [IAM service administration interface](https://console.aws.amazon.com/iamv2/home?#/home)

  + Click **Roles**.

![Role](/images/role/013.png?width==90pc)

2. Click **Create role**

![Role](/images/role/014.png?width==90pc)

3. In the **Choose a use case ** section, we click on EC2 to create an IAM role to use for the application running inside EC2.
  + Click **Next:Permissions**

![Role](/images/role/015.png?width==90pc)

4. In the Filter policies box, enter **S3**.
  + Click **AmazonS3FullAccess**, we will grant full access to access and upload files to the S3 bucket we created.
  + Click **Next: Tags**.

![Role](/images/role/016.png?width==90pc)

5. Click **Next: Review**.

6. Set Role name to **ec2roles3upload**
 - Click **Create role**.

![Role](/images/role/017.png?width==90pc)


Next, we will use this role to assign to the EC2 instance and make it possible for our application to upload files to S3 without using the access key and secret access key in the code.