# PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG - TEE0419

BÀI TẬP LỚN:
1. Viết phần mềm trên công cụ Mit App inventor
   (tập trung vào quy trình tạo ra phần mềm)
   app có 3 screen:
   + about về bản thân+nút gọi sang 2 screen còn lại
   + giải 1 bài toán đơn giản
   + sử dụng webview: hiển thị 1 trang web có sẵn, hỗ trợ giao diện điện thoại
   mô tả: thanh công cụ có gì? kéo thả + thay đổi thuộc tính: làm ntn, để làm gì?
          block: mô tả bản chất việc kéo thả block ntn?
                 ưu điểm gì so với viết code? nhược điểm?
                 copy paste block ? (backpack)
2. Viết app sử dụng Android Studio
   + Android manifest.xml  => mô tả gì? app cần quyền để do-st: khai báo ntn? để làm gì?
   + vòng đời của 1 ứng dụng android.
     code tự sinh sau khi tạo 1 project: có sẵn hàm onCreate: tại sao???
   + Code: java language. 
     app cần check xem có quyền để do-st? : code ntn? ý nghĩa?
     giao diện: (res/layout) mô tả bằng file XML + UI Design review
        + thuộc tính text, hoặc các thuộc tính khác: giá trị hardcode => lưu vào nới khác, tham chiếu tới nó:
          cú pháp của việc tham chiếu là gì?
          ưu điểm của việc tham chiếu này?
          OS hỗ trợ auto việc lấy giá trị tham chiếu theo LOCATION, LANGUAGE, THEME
          việc hỗ trợ auto này giúp app làm được điều gì?	
        + đối tượng chứa: gộp các đối tượng con lại: cùng 1 quy luật sắp xếp để hiển thị 
          các đối tượng con nằm kề nhau theo chiều dọc | hoặc ngang, gravity
     code tương tác với layout: vd hiển thị text
          mong muốn text hiển thị phù hợp với thiết lập LOCATION, LANGUAGE, THEME của người dùng
          thì làm ntn? (tránh hardcode)
     event (sự kiện) người dùng tác động vào app: CLICK vào button, click vào text,...
          với 1 sự kiện nào đó, muốn chạy 1 đoạn code để do-st
          thì LAYTOUT cần làm gì?
              CODE viết như nào (2 cách)
---------------------------
     trong app có các thư mục đặc biệt: Assets
     khi sử dụng Window Explorer để copy các files + folder vào trong Assets
     thì khi compiler: mọi file này đều đi theo app, nằm trong app
     trong app có thể truy cập được đến các file này
     cú pháp truy cập vào là gì?
     lợi ích của việc app có sẵn các files (offline cũng có)?
     ứng dụng: app hướng dẫn việc X

==> tạo app1 sử dụng cơ chế Dữ liệu chuẩn bị trước trong Assets
         format dữ liệu: tuỳ ý, nội dung tuỳ ý
         công cụ để hiển thị dữ liệu: tuỳ ý
         có cần phải tiền xử lý trước khi hiển thị ko: tuỳ ý.
         SV TỰ ĐẶT RA VẤN ĐỀ => TỰ GIẢI QUYẾT VẤN ĐỀ
         MÔ TẢ ĐƯỢC DỮ LIỆU CÓ ĐẶC THÙ GÌ
                    DÙNG THUẬT TOÁN NÀO ĐỂ XỬ LÝ DỮ LIỆU (NẾU CẦN)
                    DÙNG ĐỐI TƯỢNG NÀO ĐỂ HIỂN THỊ DỮ LIỆU.
                    (ĐỘ SÁNG TẠO LÀ KO GIỚI HẠN)
------------------------
APP2 (android studio):  tạo app tương đương với Mit App inventor
  app có 3 activity
  + activity1: about: about+nút gọi sang 2 activity còn lại
  + activity2: giải toán đơn giản (tuỳ ý). mỗi khi giải xong bài toán: gọi api tại https://k58kmt.tdh.io.vn/api
    để gửi bài toán lên đó
    {app_by:mã số sv, input: {a:1,b:2,c:3,name:"hello tắc kè"},output:{ketluan:"vô nghiệm", abc:"xyz", nghiem:3.14}}
    nhận lại json: {ok:1, stt:1234}
  + activity3: 
    dùng web-view để truy cập từ 
    1 trang web https://k58kmt.tdh.io.vn?masv=mã sv của bạn
=======================
    vết để lại: mô tả quá trình làm bài tập ra file .md => upload github
    kèm hình ảnh minh hoạ quá trình làm.

    print ra giấy đóng quyển, nộp bm.

=======================
# Bài làm
##  Viết phần mềm trên công cụ Mit App inventor
Truy cập https://appinventor.mit.edu/   
<img width="1918" height="942" alt="image" src="https://github.com/user-attachments/assets/73f05037-eabe-464d-b1e7-79bfee7667cd" />  
Chọn create app! => chọn new project   
<img width="959" height="477" alt="image" src="https://github.com/user-attachments/assets/de1f0632-5410-441f-be39-2a5aca085401" />  
Kéo Label từ thanh user interface vào giao diện và điền tên và mssv mình vào ô text trong Appearance  
Kéo 2 button và đặt tên là solve math và webview 
<img width="959" height="442" alt="image" src="https://github.com/user-attachments/assets/41e8fb61-3d60-4da5-b08d-5832485c416e" />  
Tạo thêm 2 screen và đặt tên như button  
<img width="959" height="468" alt="image" src="https://github.com/user-attachments/assets/dc337e08-b158-48e3-a16b-f600e3f18d65" />  
Trong screen solve math kéo lần lượt 2 textbox, 1 label, 1 button  
<img width="959" height="440" alt="image" src="https://github.com/user-attachments/assets/5c59c4b7-a0f0-4713-a9ae-c468b5ea4c91" />   
Trong screen webview kéo thêm webview vào giao diện  <img width="959" height="443" alt="image" src="https://github.com/user-attachments/assets/6cd2d64e-e120-4808-b32d-6fe07e20fa59" />  
Sau khi xong chuyển sang blocks  
<img width="338" height="420" alt="image" src="https://github.com/user-attachments/assets/1615a637-f607-4dd7-bd3a-194de0f02178" />

Tìm và thêm các khối (blocks) vào màn hình để định dạng cho các nút ở screen 1  
<img width="959" height="422" alt="image" src="https://github.com/user-attachments/assets/d91360a5-3913-43ec-9f49-a1ca15b1761a" />  

Làm tương tự bên screen giải toán, tùy thuộc vào bài toán mà chúng ta làm chọn những khối tương ứng  
<img width="959" height="443" alt="image" src="https://github.com/user-attachments/assets/2772db3f-3975-4f32-a156-0f6581981009" />  

Screen 3 webview, chọn các khối cho webview và gắn link url hiện thông tin cá nhân  
<img width="959" height="444" alt="image" src="https://github.com/user-attachments/assets/5fa1629d-65d3-4df2-9d76-be4ec1e682c3" />  
Kết quả demo  
<img width="390" height="625" alt="image" src="https://github.com/user-attachments/assets/8f4cc17e-98a7-4323-8637-9e2ff164f352" />  
<img width="380" height="630" alt="image" src="https://github.com/user-attachments/assets/6258ffc2-81c3-407b-9989-248366933aa1" />  
<img width="356" height="609" alt="image" src="https://github.com/user-attachments/assets/af06388d-fb7b-42d5-9e2b-39ed1b720f38" />  
### Thanh công cụ (Palette) bao gồm những gì?  
Thanh Palette là kho chứa linh kiện, phân chia theo mục đích sử dụng:  
+	User Interface (Giao diện): Cung cấp các phần tử tương tác như Button (Nút bấm), Label (Nhãn chữ), TextBox (Ô nhập liệu), và WebViewer (Trình duyệt web).  
+	Layout (Bố cục): Gồm HorizontalArrangement (Sắp xếp ngang), VerticalArrangement (Sắp xếp dọc). Đây là bộ khung quyết định cấu trúc vị trí, ngăn các linh kiện đè lên nhau lộn xộn.  
### Kéo - Thả và Thay đổi thuộc tính (Properties)  
Cách thực hiện:  
+	Chọn linh kiện từ thanh Palette rightarrow Giữ chuột và Kéo - Thả vào màn hình mô phỏng ở giữa (Viewer).  
+	Chọn linh kiện vừa thả trong danh sách Components rightarrow Nhìn sang cột Properties ở rìa phải để chỉnh sửa thông số.  
Mục đích (Để làm gì?):  
Định hình giao diện: Chỉnh sửa kích thước (Width/Height thành Fill parent để giãn vừa màn hình), màu sắc (BackgroundColor), cỡ chữ (FontSize) nhằm tạo ra trải nghiệm người dùng (UI/UX) tốt nhất.  
Đảm bảo tính chính xác cho Logic: Ví dụ, đổi thuộc tính Text của nút bấm thành "Tính Toán", hoặc tick chọn NumbersOnly cho TextBox1 để ép người dùng chỉ được nhập số, chặn đứng nguy cơ crash app do lỗi định dạng chữ.  
Định danh linh kiện: Sử dụng tính năng Rename để đổi tên mặc định (như Button1 rightarrow Button1). Việc này giúp người lập trình nhận diện chính xác linh kiện khi chuyển sang phân hệ xử lý khối.  
### Bản chất lập trình khối (Blocks logic)
Sau khi định hình xong vỏ bọc giao diện, tư duy logic của phần mềm sẽ được hiện thực hóa tại môi trường Blocks.
### Bản chất của việc kéo thả Block  
Lập trình khối thực chất là hình thức Lập trình trực quan (Visual Programming) dựa trên kiến trúc Hướng sự kiện (Event-driven):  
•	Mỗi khối lệnh (Block) là một đoạn mã nguồn phức tạp (Java/Android SDK) đã được đóng gói sẵn thành một hình khối trực quan có màu sắc riêng.  
•	Việc lắp ghép các khối thực chất là xây dựng các hàm điều kiện và vòng lặp. Các khối được thiết kế các khớp nối âm - dương khác nhau. Hệ thống chỉ cho phép các khối khớp lại khi và chỉ khi chúng đồng nhất về mặt logic và kiểu dữ liệu (ví dụ: Không thể nhét một khối văn bản Text vào vị trí yêu cầu một tham số số học Math).  
### So sánh với Lập trình viết code truyền thống (Text-based)
<img width="886" height="374" alt="image" src="https://github.com/user-attachments/assets/036a4469-6f1e-433d-a343-b8e7359bc1a3" />  
### Cơ chế Sao chép - Dán khối bằng Balo (Backpack)  
Nhờ có Backpack, lập trình viên chỉ cần tạo cấu trúc này một lần, sao chép vào balo và thả ra ở màn hình tiếp theo, tối ưu hóa tốc độ phát triển phần mềm.  

## Viết app sử dụng Android Studio
Tạo dự án  
<img width="1019" height="650" alt="image" src="https://github.com/user-attachments/assets/de4d4fa6-6c43-4f4c-9066-85a3fb565226" />  
Khai báo quyền Internet trong AndroidManifest.xml:  
<uses-permission android:name="android.permission.INTERNET" />  
Cho phép truyền dữ liệu không mã hóa trên các thiết bị Android cũ:  
android:usesCleartextTraffic="true"  

<img width="1019" height="538" alt="image" src="https://github.com/user-attachments/assets/d51b3e0e-6c3d-47bb-9bfa-bdf9e7826987" />  
<img width="1019" height="531" alt="image" src="https://github.com/user-attachments/assets/ae58b215-fcc8-473d-a554-6fa29b9e1a89" />  
