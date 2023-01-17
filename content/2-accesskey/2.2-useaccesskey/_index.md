+++
title = "Use access key"
weight = 2
chapter = false
pre = "<b>2.2 </b>"
+++


#### Using access key

1. Go back to the interface of the EC2 server we connected to.
  + Run the following command to install the AWS SDK for Python.

```
sudo yum install pip -y
sudo pip install boto3
```

2. After the installation is complete, run the following command to create a test.txt file for us to test upload.

```
touch test.txt
```

3. Run the following command to create the python application file.
 + Note that the <ACCESSKEY> , <SECRETACCESSKEY> and <S3BUCKETNAME> values ​​match your values.

```bash
touch upload-s3-usingaccesskey.py
echo "import boto3" > upload-s3-usingaccesskey.py
echo "s3 = boto3.client( 's3', aws_access_key_id='<ACCESSKEY>', aws_secret_access_key='<SECRETACCESSKEY>')" >> upload-s3-usingaccesskey.py
echo "s3.upload_file('test.txt', '<S3BUCKETNAME>', 'test.txt')" >> upload-s3-usingaccesskey.py
```

4. Let's run our python application to upload files to the S3 bucket.

```
python upload-s3-usingaccesskey.py
```

5. Access the S3 service interface.
  + Click S3 bucket **s3-instancerole-001**.
  + Check that the file has been successfully uploaded to the S3 bucket.

![Role](/images/role/012.png?featherlight=false&width=90pc)

When we use the access key we are running the application with full S3 service admin rights granted to the IAM user **iamaccesskey** that we created. Using the above access key will be very dangerous because it is easy to reveal the access key information when we upload the code to public repos like GitHub, for example.
Putting the access key directly into the code is not recommended because it leads to security risks, in the next section instead of using the access key, we will try to use the IAM role.