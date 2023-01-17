+++
title = "Dọn dẹp tài nguyên"
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

Bạn sẽ dọn dẹp tài nguyên theo thứ tự sau:

#### Xoá S3 bucket

1. Truy cập vào [giao diện quản lý của dịch vụ S3](https://s3.console.aws.amazon.com/s3/home?region=ap-southeast-1&region=ap-southeast-1)
  + Click chọn S3 bucket **s3-instancerole-001**.
  + Click **Empty**.

![Role](/images/role/c01.png?featherlight=false&width=90pc)

2. Điền **permanently delete** để xác nhận, sau đó click **Empty** để xóa toàn bộ dữ liệu trong S3 bucket.
  + Click **Exit** để trở lại giao diện S3.

3. Click chọn S3 bucket **s3-instancerole-001** , sau đó click **Delete**.
 
![Role](/images/role/c02.png?featherlight=false&width=90pc)

4. Điền tên bucket sau đó click **Delete bucket** để xóa S3 bucket.

#### Xoá EC2 Instance

1. Truy cập vào [giao diện quản lý dịch vụ EC2](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#Instances:)
  + Click chọn Instance chúng ta tạo cho bài lab.
  + Click **Instance state**.
  + Click **Terminate instance** , sau đó click **Terminate** để xác nhận.
 
  ![Role](/images/role/c03.png?featherlight=false&width=90pc)

2. Truy cập vào [giao diện quản lý dịch vụ IAM](https://console.aws.amazon.com/iamv2/home#/users)
  + Click **Users**
  + Click chọn user **iamaccesskey**.
  + Click **Delete**. Điền tên user **iamaccesskey** và click **Delete**.

![Role](/images/role/c04.png?featherlight=false&width=90pc)

3. Click **Roles**.
  + Điền **ec2** để tìm role chúng ta đã tạo.
  + Click chọn role **ec2roles3upload**.
  + Click **Delete**. Điền tên role **ec2roles3upload** và click **Delete** để xóa IAM Role.

![Role](/images/role/c05.png?featherlight=false&width=90pc)