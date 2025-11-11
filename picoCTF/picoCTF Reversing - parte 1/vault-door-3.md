## Descripción del reto
This vault uses for-loops and byte arrays.The source code for this vault is here: [VaultDoor3.java](https://challenge-files.picoctf.net/c_fickle_tempest/4cff24ee8b551078be8c14758fae20ab4a2dca78746aef367bc854491b8ee465/VaultDoor3.java)

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/reversing/parte-1]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/4cff24ee8b551078be8c14758fae20ab4a2dca78746aef367bc854491b8ee465/VaultDoor3.java
--2025-11-10 20:32:39--  https://challenge-files.picoctf.net/c_fickle_tempest/4cff24ee8b551078be8c14758fae20ab4a2dca78746aef367bc854491b8ee465/VaultDoor3.java
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.96, 3.174.207.121, 3.174.207.125, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.96|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1473 (1.4K) [application/octet-stream]
Saving to: ‘VaultDoor3.java’

VaultDoor3.java                         100%[============================================================================>]   1.44K  --.-KB/s    in 0s      

2025-11-10 20:32:40 (39.4 MB/s) - ‘VaultDoor3.java’ saved [1473/1473]

```

```Java
import java.util.*;
  

class VaultDoor3 {
	public static void main(String args[]) {
		VaultDoor3 vaultDoor = new VaultDoor3();
		Scanner scanner = new Scanner(System.in);
		System.out.print("Enter vault password: ");
		String userInput = scanner.next();
		String input = userInput.substring
		("picoCTF{".length(),userInput.length()-1);

		if (vaultDoor.checkPassword(input)) {
			System.out.println("Access granted.");
		} else {
			System.out.println("Access denied!");
		}
	}
// Our security monitoring team has noticed some intrusions on some of the
// less secure doors. Dr. Evil has asked me specifically to build a stronger
// vault door to protect his Doomsday plans. I just *know* this door will
// keep all of those nosy agents out of our business. Mwa ha!
//
// -Minion #2671

	public boolean checkPassword(String password) {
		if (password.length() != 32) {
			return false;
		}
		char[] buffer = new char[32];
		int i;
		for (i=0; i<8; i++) {
			buffer[i] = password.charAt(i);
		}
		for (; i<16; i++) {
			buffer[i] = password.charAt(23-i);
		}
		for (; i<32; i+=2) {
			buffer[i] = password.charAt(46-i);
		}
		for (i=31; i>=17; i-=2) {
			buffer[i] = password.charAt(i);
		}
		String s = new String(buffer);
		return s.equals("jU5t_a_sna_3lpm1cg04e_u_4_m6rb42");
	}
}
```

```Python
def checkPassword(password):
	if not len(password) == 32:
	return False
	buffer = [""] * 32

	for i in range(8):
		buffer[i] = password[i]

	for i in range(8, 16):
		buffer[i] = password[23 - i]

	for i in range(16, 32, 2):
		buffer[i] = password[46 - i]

	for i in range(31, 16, -2):
		buffer[i] = password[i]
	
	print(''.join(buffer)) # Combine and print the reconstructed password

checkPassword("jU5t_a_sna_3lpm1cg04e_u_4_m6rb42")
```


picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_e60bc2}
## Notas


## Referencia
