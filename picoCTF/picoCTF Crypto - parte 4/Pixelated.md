## Descripción del reto
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled2.png)

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/pixelated]
└─$ wget https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled1.png
--2025-11-02 13:35:16--  https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197172 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png                          100%[============================================================================>] 192.55K  1015KB/s    in 0.2s    

2025-11-02 13:35:17 (1015 KB/s) - ‘scrambled1.png’ saved [197172/197172]

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/pixelated]
└─$ wget https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled2.png
--2025-11-02 13:35:32--  https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png                          100%[============================================================================>] 192.55K  1.00MB/s    in 0.2s    

2025-11-02 13:35:33 (1.00 MB/s) - ‘scrambled2.png’ saved [197173/197173]

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-4/pixelated]
└─$ ls
scrambled1.png  scrambled2.png
```

```python
from PIL import Image
import numpy as np
import os

file_names = ["/home/kali/picoCTF/crypto/parte-4/pixelated/scrambled1.png", "/home/kali/picoCTF/crypto/parte-4/pixelated/scrambled2.png"]

img_data = [np.asarray(Image.open(f'{name}')) for name in file_names]
data = img_data[0].copy() + img_data[1].copy()
new_image = Image.fromarray(data)
new_image.save("out.png", "PNG")
```

![[Pasted image 20251102130618.png]]

picoCTF{da8fcef8}
## Notas


## Referencia
