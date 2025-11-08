## Descripción del reto
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.Download the message [here](https://artifacts.picoctf.net/c/182/message.txt).

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ wget https://artifacts.picoctf.net/c/182/message.txt
--2025-11-08 13:51:22--  https://artifacts.picoctf.net/c/182/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 638 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                             100%[============================================================================>]     638  --.-KB/s    in 0s      

2025-11-08 13:51:22 (15.7 MB/s) - ‘message.txt’ saved [638/638]

┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ cat message.txt 
SYTe (eakdy tkd sjbyndr yar thjm) jdr j yobr kt skxbnyrd ersndzyo skxbryzyzkc. Skcyreyjcye jdr bdrercyrq gzya j ery kt sajhhrcmre gazsa yrey yarzd sdrjyzwzyo, yrsaczsjh (jcq mkkmhzcm) evzhhe, jcq bdklhrx-ekhwzcm jlzhzyo. Sajhhrcmre nenjhho skwrd j cnxlrd kt sjyrmkdzre, jcq garc ekhwrq, rjsa ozrhqe j eydzcm (sjhhrq j thjm) gazsa ze enlxzyyrq yk jc kchzcr eskdzcm erdwzsr. SYTe jdr j mdrjy gjo yk hrjdc j gzqr jddjo kt skxbnyrd ersndzyo evzhhe zc j ejtr, hrmjh rcwzdkcxrcy, jcq jdr akeyrq jcq bhjorq lo xjco ersndzyo mdknbe jdkncq yar gkdhq tkd tnc jcq bdjsyzsr. Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS} 
```

![[Pasted image 20251108125329.png]]

- Cambia la `J` por la letra `Q`
PICOCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}
## Notas


## Referencia
