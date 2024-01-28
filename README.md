<p align="center">
   <a href="https://www.uit.edu.vn/">
      <img src="https://i.imgur.com/WmMnSRt.png" border="none">
   </a>
</p>
<h1 align="center">
    CS114.O11.KHCL - Machine Learning
</h1>

<h2>
   Giới thiệu môn học   
</h2>

- **Tên môn học:** Machine Learning
- **Mã môn học:** CS114
- **Mã lớp:** CS114.O11.KHCL
- **Năm học:** HK1 (2023-2024)
- **Giảng viên:** Lê Đình Duy - Phạm Nguyễn Trường An

<h2>
   Giới thiệu nhóm
</h2>

- **Thông tin thành viên** 

<table align="center">
      <tr>
       <th>Họ và Tên</th>
       <th>MSSV</th>
       <th>Github</th>
       <th>Email</th>
      </tr>
      <tr>
       <td>Trương Đăng Nghĩa</td>
       <td>20526158</td>
       <td> https://github.com/nyclone569</td>
       <td>20521658@gm.uit.edu.vn</td>  
      </tr>
      <tr>
       <td>Lê Phước Trung</td>
       <td>20522069</td>
       <td> https://github.com/Trungght453</td>
       <td>20522069@gm.uit.edu.vn</td>  
      </tr>
</table>


<h2>
  Chủ đề báo cáo 
</h2>

- **Tên đồ án:** Phân loại và đếm số lượng xe trên một đoạn đường
- **Dataset:** 
   + [train/val/test dataset](https://drive.google.com/drive/folders/16QD6sQum9BxxW_95U2R7DXc7S13_nABr?usp=drive_link)
   + [video test](https://drive.google.com/file/d/126iSbmJBf5OQ2I_vBrvfmfDSF6l5YtCB/view?usp=drive_link)
<h3>
  Mô tả đồ án
</h3>

<h3>
  1. Mô tả bài toán
</h3>

**Ngữ cảnh ứng dụng**: 

<p align="justify"> 
   Đồ án làm về việc đếm số lượng xe trên một đoạn đường sử dụng machine learning, có ứng dụng là giúp quản lý trình trạng giao thông hiệu quả hơn. 
</p>

<p align="justify"> 
   Kết quả của bài toán có thể được sử dụng để thiết kế đường qua lại, input đầu vào là một đoạn video ngắn ghi lại hoạt động giao thông xe cộ qua lại trong 1 khoảng thời gian, trong điều kiện ánh sáng bình thường, đầu ra là một con số thể hiện số lượng xe mỗi loại và tổng số lượng phương tiện trong thời lượng video.
</p>
   
**Input**
+ Một đoạn video ghi lại giao thông trên phố, góc nhìn từ trên cao hướng xuống.

**Output**
<p align="justify"> 
Video chứa các thông tin:
</p>
+ Nhãn loại xe detect được.
+ Số lượng xe lưu thông.

<h3>
  2. Mô tả bộ dữ liệu
</h3>

**Thu thập và xử lý dữ liệu**

<p align="justify"> 
   -	Dữ liệu train (cho object detection) được nhóm sử dụng video quay lại được trên đoạn đường Nguyễn Văn Cừ, Quận 5 (đối diện trường Lê Hồng Phong), ở vị trí trên cầu, góc quay hướng xuống quay lại 2 làn đường, vào khoảng 17 giờ chiều trong điều kiện thời tiết trời nắng. 
</p>
   
<p align="justify"> 
   Video có thời lượng khoảng 3 phút với 30fps (sử dụng điện thoại để quay), sau đó nhóm sử dụng script để tách từng frame ra và label thủ công nhờ sự trợ giúp của roboflow, ứng với mỗi ảnh là một file .txt bao gồm mỗi dòng là một object, chứa thông tin id, center_x, center_y, width và height. 
</p>

**Số lượng, độ đa dạng**

Tổng cộng 2109 tấm ảnh

Số lượng mỗi class bao gồm 24251 class motorbike, 3746 class car và 135 class bus.

Các nhãn của bộ dataset

+ Bus

+ Car

+ Motorbike

**Thao tác tiền xử lí**

Để làm đầy dữ liệu đầu vào, nhóm sử dụng 1 số phương pháp sau: Xoay ảnh, điểu chỉnh mức sáng, điều chỉnh độ tương phản của những tấm ảnh. 

**Phân chia dữ liệu**
- 70% dùng để train
- 10% trong train dùng để làm validation
- 15% dùng để test

<h3>
   3. Mô tả về thuật toán máy học
</h3>

** Training và evaluate:  **

<p align='justify'>
   Sử dụng model yolov8: là một mô hình phát hiện đối tượng được phát triển bởi nhóm Ultralytics. YOLOv8 là phiên bản mới nhất trong dòng mô hình YOLO, kế thừa các ưu điểm của các phiên bản trước và cải tiến thêm một số điểm quan trọng.
</p>

** Testing multiple object tracking: **
<p align='justify'>
   Sử dụng thuật toán Bytetrack kết hợp với supervision để đếm số lượng phương tiện lưu thông
</p>

<h3>
   4. Cài đặt:
</h3>

Link colab: https://colab.research.google.com/drive/19cs5mvy5M_ip_YsAFNamTIZGVs9HKcss?usp=sharing



<h3>
   5. Đánh giá,kết quả và kết luận
</h3>

Kết quả đánh giá cho object detection:


<img src = 'https://private-user-images.githubusercontent.com/140532323/300245749-a78a4a10-c657-4315-b7cf-846e32569147.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Mjc5NjEsIm5iZiI6MTcwNjQyNzY2MSwicGF0aCI6Ii8xNDA1MzIzMjMvMzAwMjQ1NzQ5LWE3OGE0YTEwLWM2NTctNDMxNS1iN2NmLTg0NmUzMjU2OTE0Ny5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQwNzQxMDFaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xMTUwNmQ4YzNiZGQ5ZTI3MGM1NWU1MTUwNDY4NjFlYWY1Njg5YjAzNzk2MjM5YzczYjkzMWFkMDc2MDI3NThhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.aU8ZKG2XZDZOVUGrlBbNkpRp4qZEMFLHAfuHvpDIrQ8' style="width:40%;height:40%;">
</img>

<p align='justify'>
	Dựa vào bảng trên cho thấy khả năng phát hiện lớp car có độ chính xác cao, tỉ lệ bỏ sót rất thấp (Precision 0.9, Recall 0.97 và mAP50 0.98), tuy nhiên model vẫn còn gặp khó khăn với class bus (Precision 0.53, Recall 0.48 và mAP50 0.48), nguyên nhân do dữ liệu của lớp bus khá ít.
</p>

Kết quả đánh giá cho vehicle counting: 

<img src = 'https://private-user-images.githubusercontent.com/140532323/300245849-569f9a9e-c1f8-4f02-ab16-95b5b3c74044.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0MjgwNjYsIm5iZiI6MTcwNjQyNzc2NiwicGF0aCI6Ii8xNDA1MzIzMjMvMzAwMjQ1ODQ5LTU2OWY5YTllLWMxZjgtNGYwMi1hYjE2LTk1YjViM2M3NDA0NC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQwNzQyNDZaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT00ZTJhMzNjODJmY2UyOWFlOGNjZWI5OTdjODNjMTMyZDA2MjI0YmM5OWY3OGI2ZWUxYzdkYjFmYzQzNGUzNGQzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.0otAHxjEyrc5wtK1No_MU-Qi2-ICEapLYd6kvaVbDUE' style="width:40%;height:40%;">
</img>




