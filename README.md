# Linux İşletim Sistemi Üzerinde Tersine Mühendislik

Bu yazı, [Reverse Engineering a Linux executable – hello world](https://www.codementor.io/packt/reverse-engineering-a-linux-executable-hello-world-rjceryk5d) adresinin Türkçe diline çevirisini içermektedir. Hatalar veya katkı için iletişime geçebilirsiniz.

Başlamak için küçük bir program yazacağız. Ama başlamadan önce bize gerekli araçların sistemimizde yüklü olduklarından emin olmamız gerek. Bir terminal açın ve aşağıdaki kodu girin. Bu kod ile sistemimize eğer yüklü değilse GCC derleyici araç takımını kurmuş olacağız. Eğer önceden yüklemişseniz, zaten kurulu olduğunu söyleyen bir yanıt alacaksanız. Tabi bu komutu çalıştırabilmek için yönetici izinlerine sahip olmalısınız. 

```bash
sudo apt install gcc
```

Derleyicimizi yükledikten sonra şu küçük programı *hello.c* adında bir dosyaya kaydedin.

```c
#include <stdio.h>
void main(void)
{
    printf ("hello world!\n");
}
```

Programı derleyip, çalıştırılabilir bir hale getirmek için ise yine terminal üzerinde şu komutu kullanın:

```bash
gcc main.c -o main
```

Son adımda ise programı çalıştırıp, sonucu görelim:

```bash
./hello
```

Terminal ekranında `hello world!` yazısını görmelisiniz. 

Programımızı hazırladıktan sonra tersine mühendislik işlemlerine geçebiliriz.

### dlroW olleH

