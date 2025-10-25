## Descripción del reto
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/45a9df82c8f05fd74b8547d157ae6b1be6ba783a2bad55c6f8c664e4609d88ac/myNetworkTraffic.pcap) and try to get the flag.

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/45a9df82c8f05fd74b8547d157ae6b1be6ba783a2bad55c6f8c664e4609d88ac/myNetworkTraffic.pcap
--2025-10-25 17:51:02--  https://challenge-files.picoctf.net/c_verbal_sleep/45a9df82c8f05fd74b8547d157ae6b1be6ba783a2bad55c6f8c664e4609d88ac/myNetworkTraffic.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.125, 3.174.207.121, 3.174.207.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.125|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1452 (1.4K) [application/octet-stream]
Saving to: ‘myNetworkTraffic.pcap’

myNetworkTraffic.pcap                           100%[====================================================================================================>]   1.42K  --.-KB/s    in 0s      

2025-10-25 17:51:03 (29.8 MB/s) - ‘myNetworkTraffic.pcap’ saved [1452/1452]

┌──(kali㉿kali)-[~/picoCTF/Forensic/tarea_3]
└─$ tshark -r myNetworkTraffic.pcap -Y "tcp.len==12 || tcp.len==4" -T fields -e frame.time -e tcp.segment_data | sort -k4 | awk '{print $6}' | xxd -p -r | base64 -d
tshark: Error processing rsa_privkeys:
Error loading RSA key file /home/kali/picoCTF/Forensic/parte-3/picopico.key: No such file or directory
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_f318db22}    
```

## Notas


## Referencia
