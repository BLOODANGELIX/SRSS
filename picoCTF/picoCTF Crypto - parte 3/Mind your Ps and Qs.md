## Descripción del reto
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/crypto/parte-3]
└─$ wget https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values               
--2025-10-30 21:32:05--  https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: ‘values’

values                                  100%[============================================================================>]     206  --.-KB/s    in 0s      

2025-10-30 21:32:06 (345 MB/s) - ‘values’ saved [206/206]

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-3]
└─$ file values    
values: ASCII text

┌──(kali㉿kali)-[~/picoCTF/crypto/parte-3]
└─$ cat values    
Decrypt my super sick RSA:
c: 861270243527190895777142537838333832920579264010533029282104230006461420086153423
n: 1311097532562595991877980619849724606784164430105441327897358800116889057763413423
e: 65537   
```

```python
c = 861270243527190895777142537838333832920579264010533029282104230006461420086153423

n = 1311097532562595991877980619849724606784164430105441327897358800116889057763413423

e = 65537

p = 1955175890537890492055221842734816092141

q = 670577792467509699665091201633524389157003

phi = (p - 1) * (q - 1)
d = pow(e, -1, phi)
m = pow(c, d, n)
m_bytes = m.to_bytes((m.bit_length() + 7) // 8, 'big')
print("Bytes descifrados (hex):", m_bytes.hex())

try:
	texto = m_bytes.decode('utf-8')
	print("Texto legible UTF-8:", texto)
except UnicodeDecodeError:
	try:
		texto = m_bytes.decode('latin-1')
		print("Texto legible Latin-1:", texto)
	except:
		print("No es texto directo, probando si es texto hexadecimal...")
		try:
			inner = bytes.fromhex(m_bytes.decode())
			print("Interpretado como HEX dentro del mensaje:", inner.decode())
		except:
			print("No es texto legible.")
```

```bash
Bytes descifrados (hex): 7069636f4354467b736d6131315f4e5f6e305f67306f645f31333638363637397d
Texto legible UTF-8: picoCTF{sma11_N_n0_g0od_13686679}
```
## Notas


## Referencia