## Descripción del reto
This service provides you an encrypted flag. Can you decrypt it with just N & e?Connect to the program with netcat:`$ nc verbal-sleep.picoctf.net 63147`The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_verbal_sleep/968ace6e870166b1d910d69fe174b6ce7de6ece89448ab5d693a19c052b3d2b4/encrypt.py).

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/tarea-4]
└─$ nc verbal-sleep.picoctf.net 61685
N: 18768048967343752622553881102912785517077066098082461171165034582680126225846674165411671099188195965781234600744199113710137505211254369029323990113598134
e: 65537
cyphertext: 15689826393158912064135252205993530393018174004634138467045055149813542494445522760207735934394705004371556042179776093649511223721324202840785182373118603

```

```python
from pwn import *
from gmpy2 import gcd, invert

def main():
	e = 65537
	items = []

	for i in range(2):
		conn = remote("verbal-sleep.picoctf.net", 61685)
		n = conn.recvline()
		conn.recvline()
		c = conn.recvline()
		
		n = int(n[2:])
		c = int(c[12:])
		
		items.append((n, c))
		conn.close()

	(n1, c1), (n2, c2) = items

	p1 = gcd(n1, n2)

	if p1 != 1:
		q1 = n1 // p1
		phi1 = (p1-1) * (q1-1)
		d1 = invert(e, phi1)
		m1 = pow(c1, d1, n1)
		
		m1_bytes = bytes.fromhex(hex(m1)[2:])
		m1_str = m1_bytes.decode("utf-8")
		
		print(m1_str)

if __name__ == "__main__":
	main()
```


```bash
┌──(kali㉿kali)-[~/Desktop]
└─$ /bin/python /home/kali/picoCTF/crypto/tarea-4/codigotarea.py
[+] Opening connection to verbal-sleep.picoctf.net on port 61685: Done
[*] Closed connection to verbal-sleep.picoctf.net port 61685
[+] Opening connection to verbal-sleep.picoctf.net on port 61685: Done
[*] Closed connection to verbal-sleep.picoctf.net port 61685
picoCTF{tw0_1$_pr!m37dbe6984}
```

picoCTF{tw0_1$_pr!m37dbe6984}
## Notas


## Referencia
