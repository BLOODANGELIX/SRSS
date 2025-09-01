## Descripción del reto
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.
## Solución

Se hace un import de la libreria base64, para poder utilizar la funcion b64decode para decodificarlo, de ahi se le agrega otro .decode() para pasarlo a base 10.
``` python
>> import base64
>>> base64.b64decode("bDNhcm5fdGgzX3IwcDM1")
b'l3arn_th3_r0p35'
>>> base64.b64decode("bDNhcm5fdGgzX3IwcDM1").decode()
'l3arn_th3_r0p35'
>>> ```

picoCTF{l3arn_th3_r0p35}
## Notas
base64 : libreria para obtener funciones de conversion a formato entendible para los sistemas.

## Referencia
[Import base64: aprende qué hacer y qué no hacer con él](https://keepcoding.io/blog/que-es-el-modulo-import-base64-en-python-y-uso/)