#ASM
Cài nasm .
Sử dụng ld có sẵn của codeblock .
##Cú pháp 
``` nasm -f {(elf)|(win32)} ***.asm -o {đường dẫn xuất file (***.o)}
    ld -m {(elf_i386)|(ip86pe)} -s -o {đường dẫn xuất file thực thi{không đuôi trong linux,đuôi .exe trong window}} ***.o
```
