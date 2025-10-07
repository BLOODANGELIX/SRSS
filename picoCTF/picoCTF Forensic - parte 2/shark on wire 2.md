## Descripción del reto
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución
- Primero descargamos el archivo, para después abrirlo con wireshark.
![[Pasted image 20251006202502.png]]

- De aquí ponemos un filtro `udp.dstport == 22` para identificar los puertos 22.
![[Pasted image 20251006202523.png]]

- De ahi notamos que en la información de los puertos, todos empiezan por 5000, a lo cual se los quitaremos y nos quedaremos con estos números: `112 105 99 111 67 84 70 123 112 49 76 76 102 51 114 51 100 95 100 97 116 97 95 118 49 97 95 115 116 51 103 48 125`.

- Se los pasaremos a un decodificador y tendremos la bandera.


picoCTF{p1LLf3r3d_data_v1a_st3g0}
## Notas


## Referencia