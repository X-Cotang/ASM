# Registers (Thanh ghi)
## Segment Registers (Thanh ghi đoạn):
- Chức năng:
-Chứa mã chương trình  
-Chứa dữ liệu và kết quả trung gian của chương trình  
-Tạo ra ngăn xếp (stack)  
- Vi xử lí 8086 có 4 thanh ghi đoạn 16bit:  
-**CS** :Thanh ghi đoạn mã  
-**DS** :Thanh ghi đoạn ngăn xếp  
-**SS** :Thanh ghi stack  
-**ES** :Thanh ghi đoạn dữ liệu phụ  
-..(ngoài ra còn có FS,GS cung cấp đoạn dữ liệu bổ sung data)  
## Data Registers (Thanh ghi dữ liệu)  
- Chức năng: Store dữ liệu  
- Thanh ghi 32 bit có chữ E ở đầu ,thanh ghi 64 có chữ R (VD: EAX,RAX)
* These 32-bit registers can be used in three ways:  
  * As complete 32-bit data registers: EAX, EBX, ECX, EDX.
  * Lower halves of the 32-bit registers can be used as four 16-bit data registers: AX, BX, CX and DX.
  * Lower and higher halves of the above-mentioned four 16-bit registers can be used as eight 8-bit data registers: AH, AL, BH, BL, CH, CL, DH, and DL.
