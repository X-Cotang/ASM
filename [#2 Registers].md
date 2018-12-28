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
  
![](https://www.tutorialspoint.com/assembly_programming/images/register1.jpg)  
AX is the primary accumulator  
BX is known as the base registerb  
CX is known as the count register  
DX is known as the data register
## Pointer Registers (Thanh ghi con trỏ)
* The pointer registers are 32-bit EIP, ESP, and EBP registers and corresponding 16-bit right portions IP, SP, and BP
  * IP (Instruction Pointer:Con trỏ lệnh): Chứa địa chỉ offset của ô nhớ chứa lệnh kế.IP kết hợp với CS cung cấp địa chỉ hiên tại của đoạn mã
  * BP (Base Pointer: Con trỏ cơ sở): Chứa địa chỉ offset của ô nhớ nằm trong stack.
  * SP (Stack Pointer: Con trỏ ngăn xếp): Chứa địa chỉ offset của đỉnh ngăn xếp.  
## Index Registers (Thanh ghi chỉ số)
  - The 32-bit index registers are ESI and EDI,16 bit :SI and DI.Được dùng để chứa địa chỉ offset của mảng nhớ nguồn và đích trong các thao tác chuỗi. DS:SI phần tử thuộc chuỗi nguồn, ES:DI phần tử thuộc chuỗi đích
  - SI (Source Index)
  - DI (Destination Index)
  ## Flag Registers (Thanh ghi cờ)
- Là các thanh ghi 16 bit nhưng chỉ có 9 bit được sử dụng  
- Cờ trạng thái : Có 6 cờ trạng thái là AF,CF,SF,PF,ZF,OF .Phản ánh các trạng thái khác nhau của kết quả sau một thao tác nào đó.
- Cờ điều khiển : Có 3 cờ điều khiển IF,TF,DF.

| Flag     |    |    |    |    | O  |  D | I | T | S | Z |   | A |   | P |   | C |
| -------- |:--:| --:| -- |:--:| --:| -- |:-:| -:|:-:| -:|:-:| -:|:-:| -:|:-:| -:|
| Bit no   | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |  


-   Overflow Flag (OF) − It indicates the overflow of a high-order bit (leftmost bit) of data after a signed arithmetic operation.

-   Direction Flag (DF) − It determines left or right direction for moving or comparing string data. When the DF value is 0, the string operation takes left-to-right direction and when the value is set to 1, the string operation takes right-to-left direction.

-   Interrupt Flag (IF) − It determines whether the external interrupts like keyboard entry, etc., are to be ignored or processed. It disables the external interrupt when the value is 0 and enables interrupts when set to 1.

-   Trap Flag (TF) − It allows setting the operation of the processor in single-step mode. The DEBUG program we used sets the trap flag, so we could step through the execution one instruction at a time.

-   Sign Flag (SF) − It shows the sign of the result of an arithmetic operation. This flag is set according to the sign of a data item following the arithmetic operation. The sign is indicated by the high-order of leftmost bit. A positive result clears the value of SF to 0 and negative result sets it to 1.

-   Zero Flag (ZF) − It indicates the result of an arithmetic or comparison operation. A nonzero result clears the zero flag to 0, and a zero result sets it to 1.

-   Auxiliary Carry Flag (AF) − It contains the carry from bit 3 to bit 4 following an arithmetic operation; used for specialized arithmetic. The AF is set when a 1-byte arithmetic operation causes a carry from bit 3 into bit 4.

-   Parity Flag (PF) − It indicates the total number of 1-bits in the result obtained from an arithmetic operation. An even number of 1-bits clears the parity flag to 0 and an odd number of 1-bits sets the parity flag to 1.

-   Carry Flag (CF) − It contains the carry of 0 or 1 from a high-order bit (leftmost) after an arithmetic operation. It also stores the contents of last bit of a shift or rotate operation.
