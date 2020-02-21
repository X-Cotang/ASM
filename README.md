# ASM
- Cài nasm .
- Sử dụng ld(linker) có sẵn của codeblock .(set path C:\Program Files (x86)\CodeBlocks\MinGW\bin )
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
#### List the available emulations:
 - elf32_x86_64: ELF for x64-32, aka x32 — 32-bit x86-64 binaries
 - elf_i386: ELF for i386 — 32-bit i386 binaries
 - i386linux: a.out for i386
 - i386pep: PE+ for x86-64 — Windows-format 64-bit binaries
 - i386pe: PE for i386 — Windows-format 32-bit binaries
```
ld --verbose; or ld -V;
```
For information about ld : ftp://ftp.gnu.org/old-gnu/Manuals/ld-2.9.1/html_node/ld_3.html
⋅⋅⋅
