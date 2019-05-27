 # NGẮT TRONG CHƯƠNG TRÌNH ASSEMLBLY
- Ngắt (Interrupt) là các tín hiệu mà các thành phần trong hệ thống, như: thiết bị ngoại vi, hệ điều hành, chương trình người sử dụng, ..., gửi đến vi xử lý (họ Intel) mỗi khi nó cần trao đổi thông tin với vi xử lý hay cần được sự phục vụ từ vi xử lý. Hay ngắn gọn nó là sự xảy ra của một điều kiện ( một sự kiện) làm cho chương trình hiện hành bị tạm ngưng trong khi điều kiện được phục vụ bởi một chương trình khác
- Ngắt cũng có thể phát sinh từ chính bên trong vi xử lý khi nó phát hiện một lỗi nghiêm trong xảy ra trong quá trình xử lý của nó.
- Khi nhận được một tín hiệu yêu cầu ngắt vi xử lý sẽ dừng ngay thao tác (lệnh) hiện tại để xem xét và đáp ứng yêu cầu ngắt đó, sau đo mới tiếp tục lại từ thao tác (lệnh) mà nó bị dừng trước đó.  
``` 
Hợp ngữ cung cấp lệnh Int để các chương trình gọi một ngắt mềm khi cần. 
Khi gọi ngắt mềm chương trình phải chỉ ra số hiệu ngắt cần gọi, khi đó hệ 
thống sẽ phải gọi thực hiện chương trình con phục vụ ngắt tương ứng để đáp ứng yêu cầu gọi này.
```
---
 ## Khi hệ thống nhận được một yêu cầu ngắt n (Int   n) từ chương trình thì nó phải:
 1. Dừng lệnh hiện tại, đưa giá trị con trỏ lệnh CS:IP hiện tại (đó chính là địa chỉ của lệnh sau lệnh gọi ngắt) vào lưu trữ ở hai phần tử trên đỉnh Stack  
 2. Xác định phần tử (địa chỉ) trong bảng vector ngắt chứa vector ngắt của ngắt n, lấy giá trị tại đây (2 phần tử liên tiếp) để đưa vào cặp thanh ghi con trỏ lệnh CS:IP (đây chính là địa chỉ của lệnh đầu tiên của chương trình con phục vụ ngắt n trong bộ nhớ)  
 3. Bắt đầu thực hiện chương trình con phục vụ ngắt cho đến khi gặp lệnh kết thúc chương trình này, đó là lệnh Iret
 4. Lấy nội dung của hai phần tử trên đỉnh Stack đặt vào lại cặp thanh ghi con trỏ lệnh để quay trở lại tiếp tục thực hiện lệnh sau lệnh gọi ngắt trong chương trình.
 
> Một ngắt mềm, hay chính xác hơn là một chương trình con phục vụ ngắt, có thể thực hiện nhiều chức năng khác nhau, mỗi chức năng này được thể hiện thông qua một con số, được gọi là số hiệu hàm của ngắt. Do đó, trước khi gọi ngắt chương trình phải chỉ rõ gọi ngắt với hàm nào, bằng cách đặt số hiệu hàm cần gọi vào thanh ghi AH.  
---
## VD:
```ASM
        Mov        Ah, 02                        ; đặt số hiệu hàm cần gọi vào AH

        Mov        DH, 10                        ; cung cấp dữ liệu vào thứ nhất vào DH

        Mov        DL, 20                        ; cung cấp dữ liệu vào thứ hai vào DL

        Int           10h                        ; gọi ngắt 10h với hàm 02. Hàm/ngắt này không

                                                            ; trả về dữ liệu kết quả.
```
Dãy lệnh trên thực hiện việc gọi hàm 02 của ngắt 10h (ngắt của BIOS), nó thực hiện việc dịch chuyển con trỏ đến dòng 10 cột 20 của màn hình văn bản.
### Tổng hợp các ngắt và các hàm : http://stanislavs.org/helppc/int_table.html
 
