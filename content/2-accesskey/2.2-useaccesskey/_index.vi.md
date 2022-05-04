+++
title = "Sử dụng access key"
weight = 2
chapter = false
pre = "<b>2.2 </b>"
+++


#### Sử dụng access key

1. Quay lại giao diện của máy chủ EC2 chúng ta đã kết nối tới.
  + Chạy câu lệnh sau để cài đặt AWS SDK cho Python.

```
sudo yum install pip -y
sudo pip install boto3 
```

2. Sau khi quá trình cài đặt hoàn tất , chạy lệnh sau để tạo ra file test.txt để chúng ta thử nghiệm upload.

```
touch test.txt
```

3. Chạy lệnh sau để tạo file ứng dụng python.
 + Lưu ý thay các giá trị <ACCESSKEY> , <SECRETACCESSKEY> và <S3BUCKETNAME> phù hợp với giá trị của bạn.

```bash
touch upload-s3-usingaccesskey.py
echo "import boto3" > upload-s3-usingaccesskey.py
echo "s3 = boto3.client( 's3', aws_access_key_id='<ACCESSKEY>', aws_secret_access_key='<SECRETACCESSKEY>')" >> upload-s3-usingaccesskey.py
echo "s3.upload_file('test.txt', '<S3BUCKETNAME>', 'test.txt')" >> upload-s3-usingaccesskey.py
```

4. Thực hiện chạy ứng dụng python của chúng ta để upload file lên S3 bucket.

```
python upload-s3-usingaccesskey.py
```

5.  Truy cập vào giao diện dịch vụ S3.
  + Click S3 bucket **s3-instancerole-001**.
  + Kiểm tra file đã được upload thành công lên S3 bucket.

![Role](/images/role/012.png?width==90pc)

Khi chúng ta sử dụng access key thì chúng ta đang chạy ứng dụng với quyền quản trị full dịch vụ S3 được cấp cho IAM user **iamaccesskey** mà chúng ta đã tạo. Việc sử dụng access key như trên sẽ rất nguy hiểm vì dễ bị lộ thông tin access key khi chúng ta upload code lên những public repo như GitHub chẳng hạn.
Việc đưa trực tiếp access key vào trong code không được khuyến khích vì dẫn tới các rủi ro trong việc bảo mật, ở phần tiếp theo thay vì sử dụng access key , chúng ta sẽ thử sử dụng IAM role nhé.