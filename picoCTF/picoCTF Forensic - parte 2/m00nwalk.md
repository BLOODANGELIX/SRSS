## Descripción del reto
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

## Solución
- Primero descargamos el archivo y vemos que tipo de archivo es.
![[Pasted image 20251006200021.png]]
![[Pasted image 20251006200039.png]]

- Después descargamos e instalamos una herramienta para convertir el archivo en `PNG`.
![[Pasted image 20251006200156.png]]
![[Pasted image 20251006200245.png]]

- Ya con la herramienta instalada procedemos a ponernos en el directorio donde tenemos el archivo `.wav` y ejecutamos la herramienta en el archivo para que lo transforme a `PNG`, con el comando `sstv -d message.wav -o flag.png`.
![[Pasted image 20251006200421.png]]
![[Pasted image 20251006195817.png]]

picoCTF{beep_boop_im_in_space}
## Notas


## Referencia