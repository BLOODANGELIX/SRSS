## Descripción del reto
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Solución
- Primero descargamos el archivo.
![[Pasted image 20251001113001.png]]

- Después utilizamos la herramienta `wireshark`, en el cual cargamos la imagen, nos vamos a Analizar -> Follow -> UDP Stream, después vamos buscando en Stream hasta encontrar la bandera.
![[Pasted image 20251001113031.png]]

## Notas


## Referencia