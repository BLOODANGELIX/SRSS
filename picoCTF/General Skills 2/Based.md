## Descripción del reto
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.

## Solución
En la primera parte el reto arrojo binarios para pasar a texto:
```
01101100 01101001 01111010 01100001 01110010 01100100

lizard
```

En seguida arrojo en octal:
```
141 156 151 155 141 164 151 157 156

animation
```

Al final arrojo en hexadecimal:
```
636f6d7075746572

computer
```

picoCTF{learning_about_converting_values_02167de8}
## Notas
- Aquí utilice CyberChef para completar los retos ya que daban 45 segundos en cada parte.

## Referencia
[CyberChef](https://michaeltri.github.io/CyberChef/?recipe=%5B%7B%22op%22%3A%22From%20Hex%22%2C%22args%22%3A%5B%22Space%22%5D%7D%5D&input=MHg3MA)