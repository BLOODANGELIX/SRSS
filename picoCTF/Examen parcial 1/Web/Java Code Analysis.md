## Descripción del reto
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/481/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:52588/).

## Solución
- Nos muestra una pagina de libros, en donde accederemos con `user`, en ambos campos.
![[Pasted image 20251008234256.png]]
![[Pasted image 20251008234527.png]]

- La inspeccionamos y nos vamos a `Storange`, en donde encontraremos el token a cambiar.
![[Pasted image 20251008234550.png]]

- Abrimos el código y nos damos cuenta que la llave secreta es: 1234.
- `JwtService.java`
![[Pasted image 20251008234713.png]]

- `SecretGenerator.java`
![[Pasted image 20251008234910.png]]

- Ahora pasamos a una pagina para cambiar el payload, en el cual le daremos el rol: Admin, userId: 2 y email: admin, y en la parte de `VERIFY SIGNATURE` sera: 1234.
![[Pasted image 20251008235127.png]]
![[Pasted image 20251008235151.png]]

- Ahora volvemos a la parte de `Storange` en la inspección de la pagina, en donde cambiaremos el token y el payload, por lo que nos genero la pagina que utilizamos antes, ahora escogemos el libro que dice `FLAG` y nos dará la bandera.
![[Pasted image 20251008235227.png]]

![[Pasted image 20251008235258.png]]

picoCTF{w34k_jwt_n0t_g00d_ca4d9701}

## Notas


## Referencia