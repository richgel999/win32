---
Description: BLOBs are used with the Diffie-Hellman/Schannel provider to export keys from, and import keys into, the cryptographic service provider (CSP).
ms.assetid: ebb85b7c-204d-4b1c-86dc-5a03c8eda47b
title: Diffie-Hellman/Schannel Key BLOBs
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Diffie-Hellman/Schannel Key BLOBs

[*BLOBs*](security.b_gly#-security-blob-gly) are used with the [*Diffie-Hellman*](security.d_gly#-security-diffie-hellman-algorithm-gly)/[*Schannel*](security.s_gly#-security-schannel-gly) provider to export keys from, and import keys into, the [*cryptographic service provider*](security.c_gly#-security-cryptographic-service-provider-gly) (CSP).

-   [Public Key BLOBs](#public-key-blobs)
-   [Private Key BLOBs](#private-key-blobs)

## Public Key BLOBs

Diffie-Hellman [*public key BLOBs*](security.p_gly#-security-public-key-blob-gly), type **PUBLICKEYBLOB**, are used to exchange the (G^X) mod P value in a Diffie-Hellman key exchange. These keys are exported and imported as a sequence of bytes with the following format.

``` syntax
PUBLICKEYSTRUC  publickeystruc;
DHPUBKEY        dhpubkey;
BYTE            y[dhpubkey.bitlen/8]; // Where y = (G^X) mod P
```

The following table describes each component of the [*key BLOB*](security.k_gly#-security-key-blob-gly).



| Field          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| dhpubkey       | A [**DHPUBKEY**](/windows/win32/Wincrypt/ns-wincrypt-_pubkey?branch=master) structure. The **magic** member must be set to 0x31484400. This hexadecimal value is the [*ASCII*](security.a_gly#-security-ascii-gly) encoding of DH1.                                                                                                                                                                                                                                                                                                                                                      |
| publickeystruc | A [**PUBLICKEYSTRUC**](/windows/win32/Wincrypt/ns-wincrypt-_publickeystruc?branch=master) structure.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| y              | A **BYTE** sequence. The y value, (G^X) mod P, is located directly after the [**DHPUBKEY**](/windows/win32/Wincrypt/ns-wincrypt-_pubkey?branch=master) structure. The length, in bytes, of the sequence is the **bitlen** member of **DHPUBKEY** divided by eight. If the length of the data that results from the calculation of (G^X) mod P is one or more bytes shorter than P divided by eight, the data must be padded with the necessary bytes (of zero value) to make the data the desired length ([*little-endian*](security.l_gly#-security-little-endian-gly) format). |



 

## Private Key BLOBs

D-H [*private key BLOBs*](security.p_gly#-security-private-key-blob-gly), type **PRIVATEKEYBLOB**, are used to export and import private information of a D-H key. These keys are exported and imported as a sequence of bytes with the following format.

``` syntax
PUBLICKEYSTRUC  publickeystruc;
DHPUBKEY        dhpubkey;
BYTE            prime[dhpubkey.bitlen/8];
BYTE            generator[dhpubkey.bitlen/8];
BYTE            secret[dhpubkey.bitlen/8];
```

The following table describes each component of the key BLOB.



| Field          | Description                                                                                                                                                                                                |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| dhpubkey       | A [**DHPUBKEY**](/windows/win32/Wincrypt/ns-wincrypt-_pubkey?branch=master) structure. The **magic** member must be set to 0x32484400. This hexadecimal value is the [*ASCII*](security.a_gly#-security-ascii-gly) encoding of DH2. |
| generator      | A **BYTE** sequence. The generator G.                                                                                                                                                                      |
| publickeystruc | A [**PUBLICKEYSTRUC**](/windows/win32/Wincrypt/ns-wincrypt-_publickeystruc?branch=master) structure.                                                                                                                                                      |
| prime          | A **BYTE** sequence. The prime modulus, P. This data must always have the most significant bit of the most significant byte set to one.                                                                    |
| secret         | A **BYTE** sequence. The secret exponent X.                                                                                                                                                                |



 

> [!Note]  
> The prime, generator, and secret values must always have the same length, in bytes. If any value is one byte or more shorter than the others, it must be padded with the necessary number of zero bytes to make them the same. The prime, generator, and secret are in [*little-endian*](security.l_gly#-security-little-endian-gly) format.

 

 

 


