## Descripción del reto
Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered.Find the PDF file here [Hidden Confidential Document](https://challenge-files.picoctf.net/c_saffron_estate/8fc7f4db4cd616afa42099769749bbf3620925ed4ee7d2037ffdbd525aa14dc6/confidential.pdf) and uncover the flag within the metadata.

## Solución

```
BLOODANGELIX-picoctf@webshell:~$ strings confidential.pdf
BLOODANGELIX-picoctf@webshell:~$ strings confidential.pdf | grep pico
BLOODANGELIX-picoctf@webshell:~$ strings confidential.pdf | less     

[1]+  Stopped                 strings confidential.pdf | less

```

- En el autor habrá un cifrado base 64 el cual deberemos decodificar.
```

BLOODANGELIX-picoctf@webshell:~$ echo "cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jOGY5MWQ2OH0" | base64 -d
picoCTF{puzzl3d_m3tadata_f0und!_c8f91d68}base64: invalid input
BLOODANGELIX-picoctf@webshell:~$ 
```

picoCTF{puzzl3d_m3tadata_f0und!_c8f91d68}

## Notas


## Referencia