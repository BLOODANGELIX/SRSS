## Descripción del reto
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Solución

```
┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2025-10-14 15:47:17--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                                    100%[====================================================================================================>]  90.36K  --.-KB/s    in 0.09s   

2025-10-14 15:47:18 (1.02 MB/s) - ‘capture.pcap’ saved [92525/92525]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2025-10-14 15:47:26--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                                    100%[====================================================================================================>]   1.66K  --.-KB/s    in 0s      

2025-10-14 15:47:26 (29.8 MB/s) - ‘picopico.key’ saved [1704/1704]

┌──(kali㉿kali)-[~/picoCTF/Forensic/parte-3]
└─$ ssldump -r capture.pcap -k picopico.key -d                                                      
New TCP connection #1: 128.237.140.23(57930) <-> 172.31.22.220(443)
1 1  0.0297 (0.0297)  C>S  Handshake
      ClientHello
        Version 3.3 
        cipher suites
        TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_GCM_SHA384
        TLS_DH_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_DSS_WITH_AES_256_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA
        TLS_RSA_WITH_AES_256_GCM_SHA384
        TLS_RSA_WITH_AES_256_CBC_SHA256
        TLS_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_GCM_SHA256
        TLS_DH_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_DSS_WITH_AES_128_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA
        TLS_RSA_WITH_AES_128_GCM_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_DHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_DSS_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_EMPTY_RENEGOTIATION_INFO_SCSV
        compression methods
                  NULL
        extensions
          server_name
              host_name: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
          ec_point_formats
            ec point format                           uncompressed
            ec point format                           ansiX962_compressed_prime
            ec point format                           ansiX962_compressed_char2

          supported_groups
            supported group                           secp256r1
            supported group                           secp521r1
            supported group             

          compress_certificate
          pwd_clear
        ja3 string: 771,49200-49196-49192-49188-49172-49162-165-161-159-107-105-104-57-55-54-49202-49198-49194-49190-49167-49157-157-61-53-49199-49195-49191-49187-49171-49161-164-160-158-103-63-62-51-49-48-49201-49197-49193-49189-49166-49156-156-60-47-49170-49160-22-16-13-49165-49155-10-255,0-11-10-27-30,,0-1-2
        ja3 fingerprint: 1630dfeca408a5ade0e583bbfd7db9ea
1 2  0.0301 (0.0003)  S>C  Handshake
      ServerHello
        Version 3.3 
        session_id[0]=

        cipherSuite         TLS_RSA_WITH_AES_256_GCM_SHA384
        compressionMethod                   NULL
        extensions
          renegotiation_info
          session_ticket
        ja3s string: 771,157,65281-35
        ja3s fingerprint: 7c02dbae662670040c7af9bd15fb7e2f
1 3  0.0301 (0.0000)  S>C  Handshake
      Certificate
1 4  0.0301 (0.0000)  S>C  Handshake
      ServerHelloDone
New TCP connection #2: 128.237.140.23(57940) <-> 172.31.22.220(443)
New TCP connection #3: 128.237.140.23(57941) <-> 172.31.22.220(443)
3 1  0.0293 (0.0293)  C>S  Handshake
      ClientHello
        Version 3.3 
        cipher suites
        TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_GCM_SHA384
        TLS_DH_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_DSS_WITH_AES_256_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA
        TLS_RSA_WITH_AES_256_GCM_SHA384
        TLS_RSA_WITH_AES_256_CBC_SHA256
        TLS_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_GCM_SHA256
        TLS_DH_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_DSS_WITH_AES_128_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA
        TLS_RSA_WITH_AES_128_GCM_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_DHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_DSS_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_EMPTY_RENEGOTIATION_INFO_SCSV
        compression methods
                  NULL
        extensions
          server_name
              host_name: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
          ec_point_formats
            ec point format                           uncompressed
            ec point format                           ansiX962_compressed_prime
            ec point format                           ansiX962_compressed_char2

          supported_groups
            supported group                           secp256r1
            supported group                           secp521r1
            supported group             

          compress_certificate
          pwd_clear
        ja3 string: 771,49200-49196-49192-49188-49172-49162-165-161-159-107-105-104-57-55-54-49202-49198-49194-49190-49167-49157-157-61-53-49199-49195-49191-49187-49171-49161-164-160-158-103-63-62-51-49-48-49201-49197-49193-49189-49166-49156-156-60-47-49170-49160-22-16-13-49165-49155-10-255,0-11-10-27-30,,0-1-2
        ja3 fingerprint: 1630dfeca408a5ade0e583bbfd7db9ea
2 1  0.0298 (0.0298)  C>S  Handshake
      ClientHello
        Version 3.3 
        cipher suites
        TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_GCM_SHA384
        TLS_DH_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_DSS_WITH_AES_256_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA
        TLS_RSA_WITH_AES_256_GCM_SHA384
        TLS_RSA_WITH_AES_256_CBC_SHA256
        TLS_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_GCM_SHA256
        TLS_DH_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_DSS_WITH_AES_128_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA
        TLS_RSA_WITH_AES_128_GCM_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_DHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_DSS_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_EMPTY_RENEGOTIATION_INFO_SCSV
        compression methods
                  NULL
        extensions
          server_name
              host_name: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
          ec_point_formats
            ec point format                           uncompressed
            ec point format                           ansiX962_compressed_prime
            ec point format                           ansiX962_compressed_char2

          supported_groups
            supported group                           secp256r1
            supported group                           secp521r1
            supported group             

          compress_certificate
          pwd_clear
        ja3 string: 771,49200-49196-49192-49188-49172-49162-165-161-159-107-105-104-57-55-54-49202-49198-49194-49190-49167-49157-157-61-53-49199-49195-49191-49187-49171-49161-164-160-158-103-63-62-51-49-48-49201-49197-49193-49189-49166-49156-156-60-47-49170-49160-22-16-13-49165-49155-10-255,0-11-10-27-30,,0-1-2
        ja3 fingerprint: 1630dfeca408a5ade0e583bbfd7db9ea
3 2  0.0297 (0.0003)  S>C  Handshake
      ServerHello
        Version 3.3 
        session_id[0]=

        cipherSuite         TLS_RSA_WITH_AES_256_GCM_SHA384
        compressionMethod                   NULL
        extensions
          renegotiation_info
          session_ticket
        ja3s string: 771,157,65281-35
        ja3s fingerprint: 7c02dbae662670040c7af9bd15fb7e2f
3 3  0.0297 (0.0000)  S>C  Handshake
      Certificate
3 4  0.0297 (0.0000)  S>C  Handshake
      ServerHelloDone
2 2  0.0303 (0.0004)  S>C  Handshake
      ServerHello
        Version 3.3 
        session_id[0]=

        cipherSuite         TLS_RSA_WITH_AES_256_GCM_SHA384
        compressionMethod                   NULL
        extensions
          renegotiation_info
          session_ticket
        ja3s string: 771,157,65281-35
        ja3s fingerprint: 7c02dbae662670040c7af9bd15fb7e2f
2 3  0.0303 (0.0000)  S>C  Handshake
      Certificate
2 4  0.0303 (0.0000)  S>C  Handshake
      ServerHelloDone
1 5  0.0596 (0.0294)  C>S  Handshake
      ClientKeyExchange
1 6  0.0596 (0.0000)  C>S  ChangeCipherSpec
1 7  0.0596 (0.0000)  C>S  Handshake
      Finished
1 8  0.0613 (0.0016)  S>C  Handshake
      SessionTicket        ticket_lifetime = 1770056496
1 9  0.0613 (0.0000)  S>C  ChangeCipherSpec
1 10 0.0613 (0.0000)  S>C  Handshake
      Finished
3 5  0.0603 (0.0306)  C>S  Handshake
      ClientKeyExchange
3 6  0.0603 (0.0000)  C>S  ChangeCipherSpec
3 7  0.0603 (0.0000)  C>S  Handshake
      Finished
2 5  0.0611 (0.0308)  C>S  Handshake
      ClientKeyExchange
2 6  0.0611 (0.0000)  C>S  ChangeCipherSpec
2 7  0.0611 (0.0000)  C>S  Handshake
      Finished
3 8  0.0614 (0.0010)  S>C  Handshake
      SessionTicket        ticket_lifetime = 1770078480
3 9  0.0614 (0.0000)  S>C  ChangeCipherSpec
3 10 0.0614 (0.0000)  S>C  Handshake
      Finished
2 8  0.0628 (0.0016)  S>C  Handshake
      SessionTicket        ticket_lifetime = 1770048816
2 9  0.0628 (0.0000)  S>C  ChangeCipherSpec
2 10 0.0628 (0.0000)  S>C  Handshake
      Finished
New TCP connection #4: 128.237.140.23(57944) <-> 172.31.22.220(443)
4 1  0.0304 (0.0304)  C>S  Handshake
      ClientHello
        Version 3.3 
        cipher suites
        TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_GCM_SHA384
        TLS_DH_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_DSS_WITH_AES_256_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA
        TLS_RSA_WITH_AES_256_GCM_SHA384
        TLS_RSA_WITH_AES_256_CBC_SHA256
        TLS_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_GCM_SHA256
        TLS_DH_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_DSS_WITH_AES_128_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA
        TLS_RSA_WITH_AES_128_GCM_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_DHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_DSS_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_EMPTY_RENEGOTIATION_INFO_SCSV
        compression methods
                  NULL
        extensions
          server_name
              host_name: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
          ec_point_formats
            ec point format                           uncompressed
            ec point format                           ansiX962_compressed_prime
            ec point format                           ansiX962_compressed_char2

          supported_groups
            supported group                           secp256r1
            supported group                           secp521r1
            supported group             

          compress_certificate
          pwd_clear
        ja3 string: 771,49200-49196-49192-49188-49172-49162-165-161-159-107-105-104-57-55-54-49202-49198-49194-49190-49167-49157-157-61-53-49199-49195-49191-49187-49171-49161-164-160-158-103-63-62-51-49-48-49201-49197-49193-49189-49166-49156-156-60-47-49170-49160-22-16-13-49165-49155-10-255,0-11-10-27-30,,0-1-2
        ja3 fingerprint: 1630dfeca408a5ade0e583bbfd7db9ea
4 2  0.0307 (0.0003)  S>C  Handshake
      ServerHello
        Version 3.3 
        session_id[0]=

        cipherSuite         TLS_RSA_WITH_AES_256_GCM_SHA384
        compressionMethod                   NULL
        extensions
          renegotiation_info
          session_ticket
        ja3s string: 771,157,65281-35
        ja3s fingerprint: 7c02dbae662670040c7af9bd15fb7e2f
4 3  0.0307 (0.0000)  S>C  Handshake
      Certificate
4 4  0.0307 (0.0000)  S>C  Handshake
      ServerHelloDone
4 5  0.0624 (0.0316)  C>S  Handshake
      ClientKeyExchange
4 6  0.0624 (0.0000)  C>S  ChangeCipherSpec
4 7  0.0624 (0.0000)  C>S  Handshake
      Finished
4 8  0.0635 (0.0010)  S>C  Handshake
      SessionTicket        ticket_lifetime = 1770100096
4 9  0.0635 (0.0000)  S>C  ChangeCipherSpec
4 10 0.0635 (0.0000)  S>C  Handshake
      Finished
4 11 0.0978 (0.0342)  C>S  application_data
    ---------------------------------------------------------------
    GET /second.html HTTP/1.1
    Host: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
    User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:68.0) Gecko/20100101 Firefox/68.0
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
    Accept-Language: en-US,en;q=0.5
    Accept-Encoding: gzip, deflate, br
    Connection: keep-alive
    Upgrade-Insecure-Requests: 1
    Pragma: no-cache
    Cache-Control: no-cache
    
    ---------------------------------------------------------------
4 12 0.0983 (0.0005)  S>C  application_data
    ---------------------------------------------------------------
    48 54 54 50 2f 31 2e 31 20 32 30 30 20 4f 4b 0d    HTTP/1.1 200 OK.
    0a 44 61 74 65 3a 20 46 72 69 2c 20 32 33 20 41    .Date: Fri, 23 A
    75 67 20 32 30 31 39 20 31 36 3a 32 37 3a 30 34    ug 2019 16:27:04
    20 47 4d 54 0d 0a 53 65 72 76 65 72 3a 20 41 70     GMT..Server: Ap
    61 63 68 65 2f 32 2e 34 2e 32 39 20 28 55 62 75    ache/2.4.29 (Ubu
    6e 74 75 29 0d 0a 4c 61 73 74 2d 4d 6f 64 69 66    ntu)..Last-Modif
    69 65 64 3a 20 4d 6f 6e 2c 20 31 32 20 41 75 67    ied: Mon, 12 Aug
    20 32 30 31 39 20 31 37 3a 33 35 3a 33 36 20 47     2019 17:35:36 G
    4d 54 0d 0a 45 54 61 67 3a 20 22 36 32 34 2d 35    MT..ETag: "624-5
    38 66 65 65 66 33 61 66 38 36 39 38 2d 67 7a 69    8feef3af8698-gzi
    70 22 0d 0a 41 63 63 65 70 74 2d 52 61 6e 67 65    p"..Accept-Range
    73 3a 20 62 79 74 65 73 0d 0a 56 61 72 79 3a 20    s: bytes..Vary: 
    41 63 63 65 70 74 2d 45 6e 63 6f 64 69 6e 67 0d    Accept-Encoding.
    0a 43 6f 6e 74 65 6e 74 2d 45 6e 63 6f 64 69 6e    .Content-Encodin
    67 3a 20 67 7a 69 70 0d 0a 50 69 63 6f 2d 46 6c    g: gzip..Pico-Fl
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
    65 6e 74 2d 4c 65 6e 67 74 68 3a 20 38 34 37 0d    ent-Length: 847.
    0a 4b 65 65 70 2d 41 6c 69 76 65 3a 20 74 69 6d    .Keep-Alive: tim
    65 6f 75 74 3d 35 2c 20 6d 61 78 3d 31 30 30 0d    eout=5, max=100.
    0a 43 6f 6e 6e 65 63 74 69 6f 6e 3a 20 4b 65 65    .Connection: Kee
    70 2d 41 6c 69 76 65 0d 0a 43 6f 6e 74 65 6e 74    p-Alive..Content
    2d 54 79 70 65 3a 20 74 65 78 74 2f 68 74 6d 6c    -Type: text/html
    0d 0a 0d 0a 1f 8b 08 00 00 00 00 00 00 03 a5 55    ...............U
    5d 77 a2 3a 14 7d 6e 7f 45 ca 6b 0b 91 91 aa bd    ]w.:.}n.E.k.....
    0b 5c ab ad d3 51 ba 1c eb 47 d5 f6 2d 42 80 30    .\...Q...G..-B.0
    81 c4 24 a8 f8 eb 6f c0 5a 3b 5d 33 b3 e6 ae cb    ..$...o.Z;]3....
    0b c9 c9 e6 64 ef 73 76 82 7b 11 b2 40 95 1c 83    ....d.sv.{..@...
    44 65 b4 7b ee 56 2f 40 51 1e 7b 06 ce 8d ee 39    De.{.V/@Q.{....9
    00 6e 82 51 58 0d f4 f0 c2 34 c1 04 af 0b 22 70    .n.QX....4...."p
    08 32 ac 10 50 28 96 c0 34 df d6 eb 50 90 20 21    .2..P(..4...P. !
    b1 f2 8c 42 45 66 c7 f8 b8 94 a3 0c 7b c6 86 e0    ...BEf......{...
    2d 67 42 19 20 60 b9 c2 b9 86 6e 49 a8 12 2f c4    -gB. `....nI../.
    1b 12 60 b3 9e 5c 01 92 13 45 10 35 65 80 28 f6    ..`..\...E.5e.(.
    ec 2b 20 13 41 f2 1f a6 62 66 44 94 97 33 9d fa    .+ .A...bfD..3..
    44 eb 8e 31 25 95 40 1c dc 4f a7 27 46 54 7f 01    D..1%.@..O.'FT..
    04 a6 9e 21 55 49 b1 4c 30 d6 fb 26 02 47 9e 91    ...!UI.L0..&.G..
    28 c5 e5 3f 10 4a 85 82 1f 1c a9 c4 5a 1d 93 04    (..?.J......Z...
    61 6e 05 2c 83 ef 01 e8 58 4d cb 86 81 94 a7 98    an.,....XM......
    95 11 8d 92 d2 d0 54 15 8e 05 51 a5 de 26 41 cd    ......T...Q..&A.
    8e 63 c6 f1 a8 9c 34 c8 f2 7e 35 1c 6f 9a 4b c2    .c....4..~5.o.K.
    33 d4 74 86 bd cb b0 0f ed 68 dc ee 38 30 6d 05    3.t......h..80m.
    2f 90 f8 b3 f1 f3 28 09 16 a2 bd bb f1 37 6c b2    /.....(......7l.
    9b 7d 19 be 6e ed 99 ae 8d 60 52 32 41 62 92 7b    .}..n....`R2Ab.{
    06 ca 59 5e 66 ac 90 c6 87 4e dc 17 52 b1 0c 1c    ..Y^f....N..R...
    84 81 88 09 a0 12 22 81 c2 19 a7 48 e1 4f 45 38    ......"....H.OE8
    68 d6 5a 85 c2 c2 3c 82 0e fc 3f 17 e8 58 58 45    h.Z...<...?..XXE
    14 c5 dd 3e a6 94 5d 81 2d 13 34 bc 70 e1 21 58    ...>..].-.4.p.!X
    39 03 1e ad e1 ae 58 58 76 cf cf dc 90 6c 40 40    9.....XXv....l@@
    91 94 9e 51 f5 16 91 1c 8b 37 ca 00 9c fd b4 fe    ...Q.....7......
    99 c9 3b ac 06 26 76 77 81 a9 6e 01 06 8a 81 5b    ..;..&vw..n....[
    30 c5 81 c0 0a 3c a1 18 eb 6d ed 9f b0 fc 98 92    0....<...m......
    6a 3a 3a cd 99 7e fa 58 60 a0 8b 81 00 27 81 2a    j::..~.X`....'.*
    f4 a4 aa 4f c9 8a 8b 6a d9 85 bc 86 b9 24 8b 81    ...O...j.....$..
    14 81 f6 64 41 2b 94 95 f2 d8 00 88 6a 4b 66 25    ...dA+......jKf%
    e0 48 4b a0 8c e5 ba 44 b0 0b 4e 32 a0 d6 51 c9    .HK....D..N2..Q.
    ad df 75 2f a0 f5 ae b7 ae fb a9 4b 23 ae 08 cb    ..u/.......K#...
    11 05 3e da a0 69 20 08 57 a7 ce 54 80 74 5c 60    ..>..i .W..T.t\`
    51 82 88 08 a9 ae 74 0b 71 0e 9e 18 e7 58 58 a9    Q.....t.q....XX.
    7c 9b 9f cc ed 7f f0 b6 3c 24 ab f9 1f bd 1c b0    |.......<$......
    50 8b 58 57 19 6b 03 1f 86 66 b3 72 af 25 29 c9    P.XW.k...f.r.%).
    6a d3 a6 bf f4 ec ba 43 e0 f2 f2 a6 75 dd db 8f    j......C....u...
    1a 62 d6 46 ab 47 c7 f6 a7 6a 3c b8 5d cf e3 c9    .b.F.G...j<.]...
    7c cf 57 7b 76 2d b3 e5 23 77 5e a2 c9 a6 7f d9    |.W{v-..#w^.....
    41 2b 35 fb 6a 3f 91 56 4a f6 ec f7 9e 75 e1 81    A+5.j?.VJ....u..
    eb 9f 88 87 79 2a ad 80 b2 22 8c 28 d2 9d a8 d8    ....y*...".(....
    a3 14 ed 20 25 2b 09 f9 b1 22 d0 b6 6c c7 6a c3    ... %+..."..l.j.
    22 0b 8f c1 df 2b 7a 1e 7d c1 b3 c6 3d ef af c3    "....+z.}...=...
    a9 3f 6e 25 be 2a af 1f e7 3c 51 4f c9 7e 91 de    .?n%.*...<QO.~..
    2c 46 76 40 fb b3 e1 37 d4 f4 7b af 5b 91 8f d7    ,Fv@...7..{.[...
    8e 7c e8 b4 c2 41 ff 7b 6f df 58 d8 ff 4b d1 7f    .|...A.{o.X..K..
    b8 56 d2 cf b7 ca af e5 f8 e9 34 9b c7 65 d8 e0    .V........4..e..
    4d be bc b3 c5 84 ac 5e 9f 6f 5f d8 60 50 b6 46    M......^.o_.`P.F
    62 dc 9a 8b 74 f0 15 3d 44 30 f7 bf ed 07 bb 87    b...t..=D0......
    9e 8c 9c 5d 63 37 18 5e de 35 da e9 64 f8 77 72    ...]c7.^.5..d.wr
    5c 78 38 cd fa 9c d5 ff 84 7f 01 14 be 28 f2 24    \x8..........(.$
    06 00 00                                           ...
    ---------------------------------------------------------------
1 11 0.3406 (0.2793)  C>S  application_data
    ---------------------------------------------------------------
    GET /starter-template.css HTTP/1.1
    Host: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
    User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:68.0) Gecko/20100101 Firefox/68.0
    Accept: text/css,*/*;q=0.1
    Accept-Language: en-US,en;q=0.5
    Accept-Encoding: gzip, deflate, br
    Connection: keep-alive
    Referer: https://ec2-18-223-184-200.us-east-2.compute.amazonaws.com/second.html
    Pragma: no-cache
    Cache-Control: no-cache
    
    ---------------------------------------------------------------
1 12 0.3410 (0.0004)  S>C  application_data
    ---------------------------------------------------------------
    48 54 54 50 2f 31 2e 31 20 32 30 30 20 4f 4b 0d    HTTP/1.1 200 OK.
    0a 44 61 74 65 3a 20 46 72 69 2c 20 32 33 20 41    .Date: Fri, 23 A
    75 67 20 32 30 31 39 20 31 36 3a 32 37 3a 30 34    ug 2019 16:27:04
    20 47 4d 54 0d 0a 53 65 72 76 65 72 3a 20 41 70     GMT..Server: Ap
    61 63 68 65 2f 32 2e 34 2e 32 39 20 28 55 62 75    ache/2.4.29 (Ubu
    6e 74 75 29 0d 0a 4c 61 73 74 2d 4d 6f 64 69 66    ntu)..Last-Modif
    69 65 64 3a 20 4d 6f 6e 2c 20 31 32 20 41 75 67    ied: Mon, 12 Aug
    20 32 30 31 39 20 31 36 3a 34 37 3a 30 35 20 47     2019 16:47:05 G
    4d 54 0d 0a 45 54 61 67 3a 20 22 36 32 2d 35 38    MT..ETag: "62-58
    66 65 65 34 36 32 62 66 32 32 37 2d 67 7a 69 70    fee462bf227-gzip
    22 0d 0a 41 63 63 65 70 74 2d 52 61 6e 67 65 73    "..Accept-Ranges
    3a 20 62 79 74 65 73 0d 0a 56 61 72 79 3a 20 41    : bytes..Vary: A
    63 63 65 70 74 2d 45 6e 63 6f 64 69 6e 67 0d 0a    ccept-Encoding..
    43 6f 6e 74 65 6e 74 2d 45 6e 63 6f 64 69 6e 67    Content-Encoding
    3a 20 67 7a 69 70 0d 0a 50 69 63 6f 2d 46 6c 61    : gzip..Pico-Fla
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
    6e 74 2d 4c 65 6e 67 74 68 3a 20 31 30 30 0d 0a    nt-Length: 100..
    4b 65 65 70 2d 41 6c 69 76 65 3a 20 74 69 6d 65    Keep-Alive: time
    6f 75 74 3d 35 2c 20 6d 61 78 3d 31 30 30 0d 0a    out=5, max=100..
    43 6f 6e 6e 65 63 74 69 6f 6e 3a 20 4b 65 65 70    Connection: Keep
    2d 41 6c 69 76 65 0d 0a 43 6f 6e 74 65 6e 74 2d    -Alive..Content-
    54 79 70 65 3a 20 74 65 78 74 2f 63 73 73 0d 0a    Type: text/css..
    0d 0a 1f 8b 08 00 00 00 00 00 00 03 4b ca 4f a9    ............K.O.
    54 a8 e6 52 50 28 48 4c 49 c9 cc 4b d7 2d c9 2f    T..RP(HLI..K.-./
    b0 52 30 2d 4a cd b5 e6 aa e5 d2 2b 2e 49 2c 2a    .R0-J......+.I,*
    49 2d d2 2d 49 cd 2d c8 49 2c 49 45 56 6a a5 60    I-.-I.-.I,IEVj.`
    0c 54 a6 60 a8 07 51 ad a0 50 92 5a 51 a2 9b 98    .T.`..Q..P.ZQ...
    93 99 9e 67 a5 90 9c 9a 07 d4 07 32 03 00 20 cc    ...g.......2.. .
    fb a0 62 00 00 00                                  ..b...
    ---------------------------------------------------------------
1 13 0.5504 (0.2093)  C>S  application_data
    ---------------------------------------------------------------
    GET /vulture.jpg HTTP/1.1
    Host: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
    User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:68.0) Gecko/20100101 Firefox/68.0
    Accept: image/webp,*/*
    Accept-Language: en-US,en;q=0.5
    Accept-Encoding: gzip, deflate, br
    Connection: keep-alive
    Referer: https://ec2-18-223-184-200.us-east-2.compute.amazonaws.com/second.html
    Pragma: no-cache
    Cache-Control: no-cache
    
    ---------------------------------------------------------------
1 14 0.5507 (0.0003)  S>C  application_data
    ---------------------------------------------------------------
    HTTP/1.1 200 OK
    Date: Fri, 23 Aug 2019 16:27:04 GMT
    Server: Apache/2.4.29 (Ubuntu)
    Last-Modified: Fri, 23 Aug 2019 16:26:33 GMT
    ETag: "112fb-590cb44f2cbe6"
    Accept-Ranges: bytes
    Content-Length: 70395
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
    Content-Type: image/jpeg
    
    ---------------------------------------------------------------
1 15 0.5802 (0.0294)  S>C  application_data
    ---------------------------------------------------------------
    ff d8 ff e0 00 10 4a 46 49 46 00 01 01 00 00 01    ......JFIF......
    00 01 00 00 ff e1 00 82 45 78 69 66 00 00 4d 4d    ........Exif..MM
    00 2a 00 00 00 08 00 05 01 1a 00 05 00 00 00 01    .*..............
    00 00 00 4a 01 1b 00 05 00 00 00 01 00 00 00 52    ...J...........R
    01 28 00 03 00 00 00 01 00 01 00 00 01 3b 00 02    .(...........;..
    00 00 00 1f 00 00 00 5a 02 13 00 03 00 00 00 01    .......Z........
    00 01 00 00 00 00 00 00 00 00 00 01 00 00 00 01    ................
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
    50 52 4f 46 49 4c 45 00 01 01 00 00 02 0c 6c 63    PROFILE.......lc
    6d 73 02 10 00 00 6d 6e 74 72 52 47 42 20 58 59    ms....mntrRGB XY
```

picoCTF{honey.roasted.peanuts}
## Notas


## Referencia