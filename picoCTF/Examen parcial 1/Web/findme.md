## Descripción del reto
Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:60407/).

## Solución
- Al principio nos da una pagina, en la cual deberemos ingresar en el usuario `test` y en password `test!`.
![[Pasted image 20251008220707.png]]

- Esto nos redirigirá a una pagina.
![[Pasted image 20251008220718.png]]

- Pero en el proceso de redireccion, las URL, nos mostraran dos direcciones distintas cuando hace el login, `http://saturn.picoctf.net:57278/next-page/id=cGljb0NURntwcm94aWVzX2Fs` y `http://saturn.picoctf.net:57278/next-page/id=bF90aGVfd2F5X2RmNDRjOTRjfQ==`. De las cuales, si sacamos la ultima parte de cada URL y las juntamos tendremos un texto codificado en Base 64 `cGljb0NURntwcm94aWVzX2FsbF90aGVfd2F5X2RmNDRjOTRjfQ==`, el cual al decodificarlo nos dará la bandera.
![[Pasted image 20251008220813.png]]
![[Pasted image 20251008220750.png]]
![[Pasted image 20251008220913.png]]

picoCTF{proxies_all_the_way_df44c94c}

## Notas


## Referencia