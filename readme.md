# ASM
- Cài nasm .
- Sử dụng ld có sẵn của codeblock .
## Compiling and Linking an Assembly Program in NASM
``` 
nasm -f {(elf)|(win32)} ***.asm -o {đường dẫn xuất file (***.o)}
```
VD: nasm -f elf hello.asm;//trên linux
nasm -f win32 hello.asm;//trên window
```
ld -m {(elf_i386)|(i386pe) {set emulation}} -s -o {đường dẫn xuất file thực thi{không đuôi trong linux,đuôi .exe trong window}} ***.o
```
VD: ld -m elf_i386 -s -o hello hello.o;//trên linux.
ld -m i386pe -s -o hello.exe hello.o
### Note
-  List the available emulations 
```
ld --verbose or ld -V
```
⋅⋅⋅
