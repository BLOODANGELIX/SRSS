## Descripción del reto
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding!The source code for this vault is here: [VaultDoor5.java](https://challenge-files.picoctf.net/c_fickle_tempest/aee691634d8cfd4a10820634bdea6b80aa104301e4b83d01fd4d176098d69e99/VaultDoor5.java)

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/reversing/parte-1]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/aee691634d8cfd4a10820634bdea6b80aa104301e4b83d01fd4d176098d69e99/VaultDoor5.java
--2025-11-10 20:55:30--  https://challenge-files.picoctf.net/c_fickle_tempest/aee691634d8cfd4a10820634bdea6b80aa104301e4b83d01fd4d176098d69e99/VaultDoor5.java
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.121, 3.174.207.96, 3.174.207.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1846 (1.8K) [application/octet-stream]
Saving to: ‘VaultDoor5.java’

VaultDoor5.java                         100%[============================================================================>]   1.80K  --.-KB/s    in 0s      

2025-11-10 20:55:30 (51.1 MB/s) - ‘VaultDoor5.java’ saved [1846/1846]

```

```Java
import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
	String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
	if (vaultDoor.checkPassword(input)) {
	    System.out.println("Access granted.");
	} else {
	    System.out.println("Access denied!");
        }
    }

    // Minion #7781 used base 8 and base 16, but this is base 64, which is
    // like... eight times stronger, right? Riiigghtt? Well that's what my twin
    // brother Minion #2415 says, anyway.
    //
    // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTY1JTY0JTMwJTYyJTM0JTMyJTM4JTM4";
        return base64Encoded.equals(expected);
    }
}
```

![[Pasted image 20251110195939.png]]

![[Pasted image 20251110195954.png]]

picoCTF{c0nv3rt1ng_fr0m_ba5e_64_ed0b4288}
## Notas


## Referencia

