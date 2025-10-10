## Descripción del reto
Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 65179 -U postgres pico`Password is `postgres`

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Parcial_1/Web]
└─$ psql -h saturn.picoctf.net -p 65179 -U postgres pico
Password for user postgres: 
psql (17.5 (Debian 17.5-1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

```

picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}

## Notas


## Referencia