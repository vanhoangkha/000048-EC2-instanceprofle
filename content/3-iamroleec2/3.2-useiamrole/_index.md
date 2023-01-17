+++
title = "Using IAM role"
weight = 2
chapter = false
pre = "<b>3.2 </b>"
+++


#### Using IAM role
1. Go to [EC2 admin interface](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#Instances:)

  + Click on the EC2 instance we created.
  + Click **Actions**.
  + Click **Security**.
  + Click **Modify IAM role**.


![Role](/images/role/018.png?featherlight=false&width=90pc)


2. Click the role **ec2roles3upload**.
  + Click **Save**.


![Role](/images/role/019.png?featherlight=false&width=90pc)


3. Return to the command line interface of the EC2 instance.
   + Run the following command to create a python application file.
   + Note that the <S3BUCKETNAME> value should match your value.

```bash
touch upload-s3-usingec2role.py
echo "import boto3" > upload-s3-usingec2role.py
echo "s3 = boto3.client( 's3' )" >> upload-s3-usingec2role.py
echo "s3.upload_file('test.txt', '<S3BUCKETNAME>', 'test.txt')" >> upload-s3-usingec2role.py
```


![Role](/images/role/020.png?featherlight=false&width=90pc)


4. Let's run our python application to upload files to the S3 bucket.

```
python upload-s3-usingec2role.py
```

5. Access the S3 service interface.
  + Click S3 bucket **s3-instancerole-001**.
  + Check that the file has been successfully uploaded to the S3 bucket.

![Role](/images/role/021.png?featherlight=false&width=90pc)

{{%notice tip%}}
When using an IAM role assigned to an EC2 instance (also known as an EC2 instance profile). The application on the EC2 server retrieves the security credentials provided by the IAM Role from the EC2 metadata **iam/ security-credentials/role -name**. The application is authorized for the actions and resources that we have defined for the IAM role through the security credentials associated with the IAM role.
{{%/notice%}}

We can check the security credentials generated for the IAM role ec2roles3upload with the following command. We can see that the credentials have an expiration time ( **Expiration** ) and will be automatically refreshed after this expiration period.

```
curl http://169.254.169.254/latest/meta-data/iam/security-credentials/ec2roles3upload
```

![Role](/images/role/022.png?featherlight=false&width=90pc)

{{%notice tip%}}
When we assign an EC2 role to an EC2 instance, the generation of temporary credentials is automatically done for us through a service called **Security Token Service** ( **STS** ). We can also use the AWS CLI in an EC2 instance that has been assigned the IAM role without any configuration. ( **aws configure** )
{{%/notice%}}

Run the following command to list the S3 bucket in the account:
```
aws s3 ls
```


![Role](/images/role/023.png?featherlight=false&width=90pc)