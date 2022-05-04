+++
title = "Tạo IAM user và access key"
weight = 1
chapter = false
pre = "<b>2.1 </b>"
+++


#### Tạo IAM user và access key

1. Truy cập vào [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iamv2/home?#/home)

  + Click **Users**.

![Role](/images/role/007.png?width==90pc)

2. Click **Add users**

![Role](/images/role/008.png?width==90pc)

3. Đặt tên User name là **iamaccesskey**.
  + Click chọn **Programmatic access**. ( Tùy chọn này cho phép sử dụng access key và secret access key cho AWS API , CLI , SDK )
  + Click **Next: Permissions**.

![Role](/images/role/009.png?width==90pc)

4. Click chọn **Attach existing policies directly**.
  + Tại ô Filter policies , điền **S3**.
  + Click chọn **AmazonS3FullAccess**, chúng ta sẽ cấp quyền full access để truy cập và upload file lên S3 bucket chúng ta đã tạo ở bước trước.
  + Click **Next: Tags**.

![Role](/images/role/010.png?width==90pc)

5. Click **Next: Review**, sau đó click **Create user**.

6. Sau khi tạo user thành công , click **Show** để hiển thị giá trị Secret access key.
  + Bạn hãy lưu cặp giá trị Access key ID + Secret access key để phục vụ cho các bước sau của workshop.
  + Bạn cũng có thể click **Download .csv** để down load Access key ID + Secret access key dưới dạng csv.

![Role](/images/role/011.png?width==90pc)

Tiếp theo chúng ta sẽ dùng access key và secret access key đã tạo để upload 1 file lên S3 bucket.