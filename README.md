# video-stego-dc instructions
## video-stego-dc-encoding
### Donwnload
```bash
imodule https://github.com/charD190523/video-stego/raw/refs/heads/main/video-stego-dc-encoding.tar
```
### Hướng dẫn thực hành
Để thực hiện giấu tin vào video, trước hết cần tạo file message.txt chứa thông điệp cần giấu, sau đó nhập thông điệp vào trong file:
```
sudo nano message.txt
```
Thực hiện extract video thành các khung hình bằng câu lệnh sau:
```python
python3 extract_frames
```
Nhập đường dẫn tuyệt đối đến video, sử dụng lệnh passwd để xem: /home/ubuntu/video/video.mp4
Các khung hình được extract thành công và lưu vào thư mục frames
Thực hiện lệnh sau để giấu thông điệp vào video:
```python
python3 encoding.py
```

Nhập đường dẫn tuyệt đối đến file message.txt, sử dụng lệnh passwd => thông điệp được giấu thành công <br>
Video được sử dụng trong bài lab có độ phân giải 640x360, có: <br>
Số khối theo chiều ngang: 640/8=80 <br>
Số khối theo chiều dọc: 360/8=45 <br>
=> Tổng số khối là 80x45 = 3600 khối <br>
Mỗi ký tự cần 8 bit => có thể giấu được thông điệp dài 450 ký tự <br>
Vì thông điệp có dạng [length]*[message] => message có thể dài tối đa 446 ký tự <br>
Thêm điệp có độ dài lớn hơn 446 ký tự vào file message.txt, thực hiện giấu tin lại và kiểm tra kết quả <br>

```python
python3 encoding.py
```
