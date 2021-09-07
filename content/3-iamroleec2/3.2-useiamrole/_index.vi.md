+++
title = "Sử dụng IAM role"
date = 2021
weight = 2
chapter = false
pre = "<b>3.2 </b>"
+++


#### Sử dụng IAM role
1. Truy cập vào [giao diện quản trị EC2](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#Instances:)

  + Click chọn EC2 instance chúng ta đã tạo.
  + Click **Actions**.
  + Click **Security**.
  + Click **Modify IAM role**.


![Role](/images/role/018.png?width==90pc)


2. Click chọn role **ec2roles3upload**.
  + Click **Save**.


![Role](/images/role/019.png?width==90pc)


3. Quay trở lại giao diện dòng lệnh của EC2 instance.
   + Chạy lệnh sau để tạo file ứng dụng python.
   + Lưu ý thay  giá trị <S3BUCKETNAME> phù hợp với giá trị của bạn.

```bash
touch upload-s3-usingec2role.py
echo "import boto3" > upload-s3-usingec2role.py
echo "s3 = boto3.client( 's3' )" >> upload-s3-usingec2role.py
echo "s3.upload_file('test.txt', '<S3BUCKETNAME>', 'test.txt')" >> upload-s3-usingec2role.py
```


![Role](/images/role/020.png?width==90pc)


4. Thực hiện chạy ứng dụng python của chúng ta để upload file lên S3 bucket.

```
python upload-s3-usingec2role.py
```

5.  Truy cập vào giao diện dịch vụ S3.
  + Click S3 bucket **s3-instancerole-001**.
  + Kiểm tra file đã được upload thành công lên S3 bucket.

![Role](/images/role/021.png?width==90pc)

{{%notice tip%}}
Khi sử dụng IAM role gán vào EC2 instance ( còn gọi là EC2 instance profile ).Ứng dụng trên máy chủ EC2  truy xuất thông tin xác thực bảo mật được cung cấp bởi IAM Role từ EC2 metadata **iam/ security-credentials/role-name**. Ứng dụng được cấp quyền cho các hành động và tài nguyên mà chúng ta đã xác định cho IAM role thông qua thông tin xác thực bảo mật được liên kết với IAM role.
{{%/notice%}}

Chúng ta có thể kiểm tra thông tin xác thực bảo mật được tạo ra cho IAM role ec2roles3upload bằng câu lệnh sau . Chúng ta có thể thấy thông tin chứng thực có thời gian hết hạn ( **Expiration** ) và sẽ được tự động làm mới sau khoản thời gian hết hạn này.

```
curl http://169.254.169.254/latest/meta-data/iam/security-credentials/ec2roles3upload
```

![Role](/images/role/022.png?width==90pc)

{{%notice tip%}}
Khi chúng ta thực hiện gán EC2 role vào EC2 instance thì việc sinh ra thông tin chứng thực tạm thời được thực thi tự động cho chúng ta thông qua một dịch vụ là **Security Token Service** ( **STS** ). Chúng ta cũng có thể sử dụng AWS CLI trong EC2 instance đã được gán IAM role mà không cần cấu hình. ( **aws configure** )
{{%/notice%}}

Chạy câu lệnh sau để liệt kê S3 bucket trong account:
```
aws s3 ls
```


![Role](/images/role/023.png?width==90pc)