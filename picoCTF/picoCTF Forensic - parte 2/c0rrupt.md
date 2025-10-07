## Descripción del reto
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Solución
- Descargamos el archivo, mostramos el contenido del archivo y como esta compuesto.
![[Pasted image 20251006194125.png]]
![[Pasted image 20251006194140.png]]

- Después modificamos con `hexeditor`:
	- Primero la cabecera que deberá ser: `89 50 4E 47 0D 0A 1A 0A`
	- Después el IHDR : `43 22 44 52` por `49 48 44 52`
	- Luego pHys: `AA 00 16 25 00 00 16 25` por `00 00 16 25 00 00 16 25`
	- En seguida el tamaño del chunk:  `AA AA FF A5` por  `00 00 FF A5`
	- Al final corregimos el chunk anterior para que diga IDAT: `AB 44 45 54` por `49 44 41 54`
![[Pasted image 20251006193947.png]]

- Con esto nos dará un archivo `PNG`, el cual se podrá abrir y nos dará la bandera.
![[Pasted image 20251006111509.png]]

picoCTF{c0rrupt10n_1847995}
## Notas


## Referencia