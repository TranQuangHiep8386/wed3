# wed3
wed3
Bài tập 3   : môn Phát triển ứng dụng trên nền web
Giảng viên  : Đỗ Duy Cốp
Lớp học phần: 58KTPM
Ngày giao   : 2025-10-24 13:50
Hạn nộp     : 2025-11-05 00:00
--------------------------------------------------
Yêu cầu     : LẬP TRÌNH ỨNG DỤNG WEB trên nền linux
1. Cài đặt môi trường linux: SV chọn 1 trong các phương án
 - enable wsl: cài đặt docker desktop
 - enable wsl: cài đặt ubuntu
 - sử dụng Hyper-V: cài đặt ubuntu
 - sử dụng VMware : cài đặt ubuntu
 - sử dụng Virtual Box: cài đặt ubuntu
2. Cài đặt Docker (nếu dùng docker desktop trên windows thì nó có ngay)
3. Sử dụng 1 file docker-compose.yml để cài đặt các docker container sau: 
   mariadb (3306), phpmyadmin (8080), nodered/node-red (1880), influxdb (8086), grafana/grafana (3000), nginx (80,443)
4. Lập trình web frontend+backend:
 SV chọn 1 trong các web sau:
 4.1 Web thương mại điện tử
 - Tạo web dạng Single Page Application (SPA), chỉ gồm 1 file index.html, toàn bộ giao diện do javascript sinh động.
 - Có tính năng login, lưu phiên đăng nhập vào cookie và session
   Thông tin login lưu trong cơ sở dữ liệu của mariadb, được dev quản trị bằng phpmyadmin, yêu cầu sử dụng mã hoá khi gửi login.
   Chỉ cần login 1 lần, bao giờ logout thì mới phải login lại.
 - Có tính năng liệt kê các sản phẩm bán chạy ra trang chủ
 - Có tính năng liệt kê các nhóm sản phẩm
 - Có tính năng liệt kê sản phẩm theo nhóm
 - Có tính năng tìm kiếm sản phẩm
 - Có tính năng chọn sản phẩm (đưa sản phẩm vào giỏ hàng, thay đổi số lượng sản phẩm trong giỏ, cập nhật tổng tiền)
 - Có tính năng đặt hàng, nhập thông tin giao hàng => được 1 đơn hàng.
 - Có tính năng dành cho admin: Thống kê xem có bao nhiêu đơn hàng, call để xác nhận và cập nhật thông tin đơn hàng. chuyển cho bộ phận đóng gói, gửi bưu điện, cập nhật mã COD, tình trạng giao hàng, huỷ hàng,...
 - Có tính năng dành cho admin: biểu đồ thống kê số lượng mặt hàng bán được trong từng ngày. (sử dụng grafana)
 - backend: sử dụng nodered xử lý request gửi lên từ javascript, phản hồi về json.
 4.2 Web IOT: Giám sát dữ liệu IOT.
 - Tạo web dạng Single Page Application (SPA), chỉ gồm 1 file index.html, toàn bộ giao diện do javascript sinh động.
 - Có tính năng login, lưu phiên đăng nhập vào cookie và session
   Thông tin login lưu trong cơ sở dữ liệu của mariadb, được dev quản trị bằng phpmyadmin, yêu cầu sử dụng mã hoá khi gửi login.
   Chỉ cần login 1 lần, bao giờ logout thì mới phải login lại.
 - hiển thị giá trị mới nhất của các thông số đang giám sát, khi click vào thì hiển thị đồ thị lịch sử quá trình thay đổi (gọi grafana iframe để hiển thị)
 - backend: Sử dụng nodered để đọc dữ liệu từ các cảm biến (có thể dùng api online để lấy dữ liệu theo giời gian thực), 
   nodered sẽ lưu dữ liệu mới nhất (dạng update) vào cơ sở dữ liệu mariadb (sử dụng phpmyadmin để tạp table và quản trị lần đầu)
   nodered sẽ lưu dữ liệu (insert) vào influxdb để lưu giá trị lịch sử, để cho grafana dùng để hiển thị biểu đồ.
5. Nginx làm web-server
 - Cấu hình nginx để chạy được website qua url http://fullname.com  (thay fullname bằng chuỗi ko dấu viết liền tên của bạn)
 - Cấu hình nginx để http://fullname.com/nodered truy cập vào nodered qua cổng 80, (dù nodered đang chạy ở port 1880)
 - Cấu hình nginx để http://fullname.com/grafana truy cập vào grafana qua cổng 80, (dù grafana đang chạy ở port 3000)

Yêu cầu sinh viên lưu code trên github
có file readme.md có hình ảnh + text: ghi lại nhật ký quá trình làm bài.

CÁCH ĐÁNH GIÁ:
1. Cài đặt được môi trường: 1đ
2. Cài đặt được các docker container với cấu hình phù hợp: 1đ
3. Web chạy được, giao diện phù hợp, chạy trên web sever nginx: 2đ
4. nodered api trả về json, test được: 2đ
5. front-end có js gọi được api nodered, nhận về json, hiển thị được kết quả từ json này. 2đ
6. Bài làm có dấu ấn, giải thích rõ ràng, hiểu vấn đề: 2đ
bài làm

<img width="648" height="404" alt="{FE1CE03C-68E1-43E8-9407-A3B183279E5E}" src="https://github.com/user-attachments/assets/9c94c680-c660-4ffd-a6ec-3229107f53ad" />

<img width="1280" height="720" alt="{8E6A0081-C2F8-4F9D-9BC7-0115A9B69694}" src="https://github.com/user-attachments/assets/0c9c9ad1-2f87-4694-a879-354f318a964c" />

<img width="1280" height="720" alt="{2C387997-B56E-43F3-8F7B-4FD777BADB4A}" src="https://github.com/user-attachments/assets/e1f090a4-0ef6-4919-8f14-cd52668ec937" />

<img width="1275" height="715" alt="{A9E780D9-40DE-4CAF-97E2-E98170EF5CA6}" src="https://github.com/user-attachments/assets/a11e0fce-3325-4d5f-a275-a3d170e8a95f" />

<img width="837" height="544" alt="{A4B6C5AF-20BA-4E3A-9EB2-26882BA2182C}" src="https://github.com/user-attachments/assets/096e62c7-daa1-4556-a5ab-07240b783130" />

<img width="1270" height="588" alt="{AC692CA0-2470-41CF-98C6-C3751C53FB86}" src="https://github.com/user-attachments/assets/b00ac49a-ae2b-41cc-ac50-a2e039e16f75" />

<img width="823" height="494" alt="{EB23C82C-1F1F-42C0-9CCF-926C681CBFD3}" src="https://github.com/user-attachments/assets/0420127c-7986-4bf0-ac56-3431ea4eb01c" />

<img width="1280" height="720" alt="{ACFDB0EA-FC3A-4C4D-8264-0ECAF688D51D}" src="https://github.com/user-attachments/assets/637f964e-e1bf-4eb2-b51e-8191ccff8590" />

<img width="1280" height="720" alt="{3A3A755E-6B51-4DEA-81E6-A50D7DF33FD0}" src="https://github.com/user-attachments/assets/e8dcc895-5ff7-4394-b43f-1bfe626ec192" />

<img width="1278" height="686" alt="{72D48B6E-8CD5-4E0A-95CB-F674808ECC26}" src="https://github.com/user-attachments/assets/25601433-ba40-4fec-9ce6-b3c2835a1ead" />
