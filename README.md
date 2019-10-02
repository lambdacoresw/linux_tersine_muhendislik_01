# Linux İşletim Sistemi Üzerinde Tersine Mühendislik

Bu yazı, [Reverse Engineering a Linux executable – hello world](https://www.codementor.io/packt/reverse-engineering-a-linux-executable-hello-world-rjceryk5d) adresinin Türkçe diline çevirisini içermektedir. Hatalar veya katkı için iletişime geçebilirsiniz. Yazıda anlatılanlara hakim olmak için temel seviyede Linux işletim sistemi kullanımı ve C programlama dili bilgisi gerekmektedir.

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

Programı derleyip, çalıştırmak için aşağıda gördüğünüz komutları girin:
![1.png](1.png)

Linux programımız ekrana bir mesaj iletip çalışmasını sonlandıracaktır.

##  dlroW olleH
Bir programa tersine-mühendislik uygulamadan önce dosyamız hakkında bilgi almak iyi olur. _file_ komutu ile başlayalım:
![2.png](2.png)
