+++
title = "Generate IAM user and access key"
weight = 1
chapter = false
pre = "<b>2.1 </b>"
+++


#### Generate IAM user and access key

1. Go to [IAM service administration interface](https://console.aws.amazon.com/iamv2/home?#/home)

  + Click **Users**.

![Role](/images/role/007.png?featherlight=false&width=90pc)

2. Click **Add users**

![Role](/images/role/008.png?featherlight=false&width=90pc)

3. Set User name as **iamaccesskey**.
  + Click on **Programmatic access**. ( This option allows using access key and secret access key for AWS API , CLI , SDK )
  + Click **Next: Permissions**.

![Role](/images/role/009.png?featherlight=false&width=90pc)

4. Click **Attach existing policies directly**.
  + In the Filter policies box, enter **S3**.
  + Click **AmazonS3FullAccess**, we will grant full access to access and upload files to the S3 bucket we created in the previous step.
  + Click **Next: Tags**.

![Role](/images/role/010.png?featherlight=false&width=90pc)

5. Click **Next: Review**, then click **Create user**.

6. After creating a successful user, click **Show** to display the Secret access key value.
  + Please save the Access key ID + Secret access key value pair to serve the following steps of the workshop.
  + You can also click **Download .csv** to download the Access key ID + Secret access key as csv.

![Role](/images/role/011.png?featherlight=false&width=90pc)

Next we will use the generated access key and secret access key to upload a file to the S3 bucket.