+++
title = "Tạo IAM role"
weight = 1
chapter = false
pre = "<b>3.1 </b>"
+++


#### Tạo IAM user và access key

1. Truy cập vào [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iamv2/home?#/home)

  + Click **Roles**.

![Role](/images/role/013.png?featherlight=false&width=90pc)

2. Click **Create role**

![Role](/images/role/014.png?featherlight=false&width=90pc)

3. Tại mục **Choose a use case ** chúng ta click chọn EC2 để tạo một IAM role sử dụng cho ứng dụng chạy bên trong EC2.
  + Click **Next:Permissions**

![Role](/images/role/015.png?featherlight=false&width=90pc)

4. Tại ô Filter policies , điền **S3**.
  + Click chọn **AmazonS3FullAccess**, chúng ta sẽ cấp quyền full access để truy cập và upload file lên S3 bucket chúng ta đã tạo.
  + Click **Next: Tags**.

![Role](/images/role/016.png?featherlight=false&width=90pc)

5. Click **Next: Review**.

6. Đặt Role name là **ec2roles3upload**
 - Click **Create role**.

![Role](/images/role/017.png?featherlight=false&width=90pc)


Tiếp theo chúng ta sẽ dùng role này để gán vào EC2 instance và giúp ứng dụng của chúng ta có thể upload file lên S3 mà không cần sử dụng access key và secret access key trong code.