---
title: DID
description: Decentralized Identifiers for RCL Verifiable Credentials
parent: Introduction
has_children: false
nav_order: 2
---

# Decentralized Identifier (DID)
**V1.0**

A Decentralized Identifier (DID) is used to uniquely identity the holder or issuer of a verifiable credential. The DID complies with the [W3C Specification for Decentralized Identifiers](https://www.w3.org/TR/did-1.1/) to ensure confidentiality and security of the holder's and issuer's digital identity.

# What is a DID

A DID is machine-readable and enables verifiable and decentralized identity. There are many DID methods that can be used to create the DID. These DID methods will outline the electronic format for the DID, how it is hosted and how it is resolved.  

# Cryptography

The foundation building block for a DID are Asymmetric Cryptographic Keys. A key pair is generated for the owner of a DID. A **private key** is securely held by the owner and a correspondent **public key** is distributed to the public. 

An owner of a DID will use their private key to digitally sign a digital file and send this file to a receiver's computer. The receiver's computer will then use the public key of the sender that is  publicly available  to verify the sender's signature on the digital file. When the digital signature is verified, the receiver's computer will deem the signature valid and the digital file wll be accepted.

When a DID is created, a public and private key pair is generated for the owner. The owner will download and store the private key in a secure location. The public key will be embedded in the DID. Based on the particular DID method to be used, the public key will be made publicly available by resolving the DID. The public key can then be accessed in a DID document.

# The did:jwk Method

The applications identified in these guidance documents only support the [did:jwk](https://github.com/quartzjer/did-jwk/blob/main/spec.md) method. In this method, a public and private key pair is created for the owner of the DID. The cryptographic algorithm used to created the keys is [RSA](https://datatracker.ietf.org/doc/html/rfc8017) using a key size of 2048 bit. Only this cryptographic algorithm is supported.

{: .warning }
The holder of the DID must download and save the private key in a secure location. The private key must not be shared with anyone. The holder must take the necessary precautions for the private key not be lost or stolen. A compromised private key will compromise a digital credential or a DID.

The private key will be formatted as a ``.txt`` file. If you open the text file on a computer you will see something like this:

## Sample Private Key

```
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAwrEkeoQJNuc9rpn7ybJBXoaP2znaMSYTdIkrqewKSrTPhOD7
qTgAEb4VK6WI7WEI6Lrz11tAc7y1bWZX3/PEQArRqFxIJAdo4esEtqaJVhGWe7uC
sQ6IqHs8eOB4x+maO+ej8RQe93c6OXvo1+6OVtH5ncQqTta+0qGFs7BAObOaK7Da
568nXm9iu2MtwXKl/Bs15cU4vZW4ph2ZfLOLT0TEMYCyvfKzniEkTCTJvt6Yxct2
qQSzw5Mf6nOQGoNWCPtjncoWmQYeGTsTZ03exnFtNiCnjMwqO0SAlrXWvkWB1Xrh
yQV+gij/zb2J0jDSVbMUgqOFqncBcDRmwwLNeQIDAQABAoIBAChudS7kQK2gNBUQ
cVOfqyegNjvGteNDDwNCgUjWdgSxq+7iciDgOlN08BySUe9KGXmLaZwtnSLr65l+
iX0+uGC8XnHiSDEDQOq5zc7Iovi2ylODy05NwF+MyDAqHasWfis2nbsw/IVTw0mw
y9gb+H9bN8VluYuJ2TMQzB1W2t+gac4gx8vRdWipAi+EdYdqto5gpSmBs4O3e7gD
t9du0DUd0jlZwrc1snVZawUCCafNja9iLvyYGtB7W0HTk3zgtG8qM7r3rYs0gkmX
gdosgmfe2U8/pYxKFfN/WlV53gFsyvjzV8F6mhuZ9es6rY+l719wOohzHTbtWqkK
LbT9vAkCgYEA0DFV+KSnyNN9mSzwLqG0yOCJ7HzLUErQYYTPmKsI1Skr0T5p6avy
nUSj/zPU8Hr/HZcouYobOKbybcjmEf9qqR04oiDl35CHQeA+u1203IE1t416aXPu
vWTBkR+noiN1fYjN9gUmGgMZmMvOlIM2ge1OWyddYMXa5aOSyf1CUEcCgYEA72Yp
Q+kYRmOMk0MCm5XcrKvHF1X2UKCcMgJawkYfyjOG7ETWFC2RTe5tJlQRugGj3TNg
0pY4YUGauCC/PQQINgvM7w+BYRM3UVRzpT0N4aW0Eclvfcm4enbIfzF0sMMWghDk
bxQ4ju1b5EH88BLCNFFgvKd/Xpmy6eiatsh4lD8CgYAcC0lFYQio6LQ2efMwlN/B
X1202WqZujovqLA+JGvgKteYLAwgSeU4ghKFQfohGrBa0A3QUGYyT2rAlxtGuV0o
wqLqU/wjDVjq6sYIfyrpuQ3/V7NxmQhDwtrALb9q+9PLwS3dQfxL7Lb5+hotry8c
eVbguIC/lGdUH6CaTN8t6QKBgQCv4fnNR/KqvDaqdp/y2N6BCc9CqMhHokg/QZWW
h9iRQNwOt+AkgPnxLIuKjldbthrCyB2Jeg4//egDASQfWtgBhRfyRw0B2hFZMleo
fbu2HXy3WKwN2WcsqhpRwG7/8sSVmH2L0mpfL6nEgGqpos6Fi4gr8k9UnE1jJp6M
TaqxFwKBgQDBsAWEWzlqQtAU1ohJ6ksP7+14kzJXh2WgxlQcbut1jQ2hzOtXd7mN
M2+PRxoAdhGObC9DHAHbQi9CcgUrBWBqNM6mZezziI45/xSksTXI4mjrg5NrTbLn
U5AGMCpp9BFzRS4ozQV8iFc+vVUaHTRV8xoM0LzFLFqtTAULKTzmJQ==
-----END RSA PRIVATE KEY-----
```

Using the did:jwk method, the public key is embedded in the DID. The DID is formatted as a ``.txt`` file. If you open the text file on a computer you will see something similar to this:

## Sample DID using the did:jwk Method

```
did:jwk:eyJrdHkiOiJSU0EiLCJuIjoid3JFa2VvUUpOdWM5cnBuN3liSkJYb2FQMnpuYU1TWVRkSWtycWV3S1NyVFBoT0Q3cVRnQUViNFZLNldJN1dFSTZMcnoxMXRBYzd5MWJXWlgzX1BFUUFyUnFGeElKQWRvNGVzRXRxYUpWaEdXZTd1Q3NRNklxSHM4ZU9CNHgtbWFPLWVqOFJRZTkzYzZPWHZvMS02T1Z0SDVuY1FxVHRhLTBxR0ZzN0JBT2JPYUs3RGE1NjhuWG05aXUyTXR3WEtsX0JzMTVjVTR2Wlc0cGgyWmZMT0xUMFRFTVlDeXZmS3puaUVrVENUSnZ0Nll4Y3QycVFTenc1TWY2bk9RR29OV0NQdGpuY29XbVFZZUdUc1RaMDNleG5GdE5pQ25qTXdxTzBTQWxyWFd2a1dCMVhyaHlRVi1naWpfemIySjBqRFNWYk1VZ3FPRnFuY0JjRFJtd3dMTmVRIiwiZSI6IkFRQUIifQ
```

# Resolving a DID

Computer systems that can read the DID will **resolve** the DID into a **DID Document**. You can use the [Universal Resolver](https://dev.uniresolver.io/) provided by the [Decentralized Identity Foundation (DIF)](https://identity.foundation/) to resolve a DID. Just copy the DID into the ``did-url`` textbox and click the ``Resolve`` button. The DID will be resolved into a DID document in ``json`` format that looks something like this:

## Sample DID Document using the did:jwk Method

```json
{
  "@context": [
    "https://www.w3.org/ns/did/v1",
    {
      "@vocab": "https://www.iana.org/assignments/jose#"
    }
  ],
  "id": "did:jwk:eyJrdHkiOiJSU0EiLCJuIjoid3JFa2VvUUpOdWM5cnBuN3liSkJYb2FQMnpuYU1TWVRkSWtycWV3S1NyVFBoT0Q3cVRnQUViNFZLNldJN1dFSTZMcnoxMXRBYzd5MWJXWlgzX1BFUUFyUnFGeElKQWRvNGVzRXRxYUpWaEdXZTd1Q3NRNklxSHM4ZU9CNHgtbWFPLWVqOFJRZTkzYzZPWHZvMS02T1Z0SDVuY1FxVHRhLTBxR0ZzN0JBT2JPYUs3RGE1NjhuWG05aXUyTXR3WEtsX0JzMTVjVTR2Wlc0cGgyWmZMT0xUMFRFTVlDeXZmS3puaUVrVENUSnZ0Nll4Y3QycVFTenc1TWY2bk9RR29OV0NQdGpuY29XbVFZZUdUc1RaMDNleG5GdE5pQ25qTXdxTzBTQWxyWFd2a1dCMVhyaHlRVi1naWpfemIySjBqRFNWYk1VZ3FPRnFuY0JjRFJtd3dMTmVRIiwiZSI6IkFRQUIifQ",
  "verificationMethod": [
    {
      "id": "#0",
      "type": "JsonWebKey2020",
      "controller": "did:jwk:eyJrdHkiOiJSU0EiLCJuIjoid3JFa2VvUUpOdWM5cnBuN3liSkJYb2FQMnpuYU1TWVRkSWtycWV3S1NyVFBoT0Q3cVRnQUViNFZLNldJN1dFSTZMcnoxMXRBYzd5MWJXWlgzX1BFUUFyUnFGeElKQWRvNGVzRXRxYUpWaEdXZTd1Q3NRNklxSHM4ZU9CNHgtbWFPLWVqOFJRZTkzYzZPWHZvMS02T1Z0SDVuY1FxVHRhLTBxR0ZzN0JBT2JPYUs3RGE1NjhuWG05aXUyTXR3WEtsX0JzMTVjVTR2Wlc0cGgyWmZMT0xUMFRFTVlDeXZmS3puaUVrVENUSnZ0Nll4Y3QycVFTenc1TWY2bk9RR29OV0NQdGpuY29XbVFZZUdUc1RaMDNleG5GdE5pQ25qTXdxTzBTQWxyWFd2a1dCMVhyaHlRVi1naWpfemIySjBqRFNWYk1VZ3FPRnFuY0JjRFJtd3dMTmVRIiwiZSI6IkFRQUIifQ",
      "publicKeyJwk": {
        "kty": "RSA",
        "n": "wrEkeoQJNuc9rpn7ybJBXoaP2znaMSYTdIkrqewKSrTPhOD7qTgAEb4VK6WI7WEI6Lrz11tAc7y1bWZX3_PEQArRqFxIJAdo4esEtqaJVhGWe7uCsQ6IqHs8eOB4x-maO-ej8RQe93c6OXvo1-6OVtH5ncQqTta-0qGFs7BAObOaK7Da568nXm9iu2MtwXKl_Bs15cU4vZW4ph2ZfLOLT0TEMYCyvfKzniEkTCTJvt6Yxct2qQSzw5Mf6nOQGoNWCPtjncoWmQYeGTsTZ03exnFtNiCnjMwqO0SAlrXWvkWB1XrhyQV-gij_zb2J0jDSVbMUgqOFqncBcDRmwwLNeQ",
        "e": "AQAB"
      }
    }
  ]
}
```

You can see the public key in the DID document inside the ``publicKeyJwk`` parameter. The public key is fomatted as a [JSON Web Key (JWK)](https://datatracker.ietf.org/doc/html/rfc7517). The JWK extracted from the DID document is shown below:

## Sample Public Key as a JSON Web Key (JWK)

```json
{
  "kty": "RSA",
  "n": "wrEkeoQJNuc9rpn7ybJBXoaP2znaMSYTdIkrqewKSrTPhOD7qTgAEb4VK6WI7WEI6Lrz11tAc7y1bWZX3_PEQArRqFxIJAdo4esEtqaJVhGWe7uCsQ6IqHs8eOB4x-maO-ej8RQe93c6OXvo1-6OVtH5ncQqTta-0qGFs7BAObOaK7Da568nXm9iu2MtwXKl_Bs15cU4vZW4ph2ZfLOLT0TEMYCyvfKzniEkTCTJvt6Yxct2qQSzw5Mf6nOQGoNWCPtjncoWmQYeGTsTZ03exnFtNiCnjMwqO0SAlrXWvkWB1XrhyQV-gij_zb2J0jDSVbMUgqOFqncBcDRmwwLNeQ",
  "e": "AQAB"
}
```

# Distributing a Public Key

When you provide your DID to a computer, the computer system would be able to resolve the DID and extract your public key from it. The computer can then use your public key to verify your digital signature when you sign a digital file with your private key.

# How DIDs are used

## Issuer

An issuer will use their private key to digitally sign a verifiable credential that they issue to a holder. The verifiable credential will contain the DID of the issuer embedded in the credential itself. A verifying computer system will then extract the public key from the issuer's DID and use it to verify the issuer's digital signature on the credential. If the signature is verified, the digital credential will be deemed valid by the computer system. 

## Holder

A holder of a credential will add their DID into a wallet application. Before they can add the DID, they must supply their private key to demonstrate that they own the DID. The wallet application will verify that the public key contained in the DID matches the correspondent private key supplied by the holder. If the keys match, the the wallet application will accept the holder's DID into the store. 

{: .warning }
A wallet application will not copy, share or store the holder's private key in any form. It will only use the private key to verify the holder's DID. The holder's private key will only be controlled by and stored by the holder using the holder's choice of storage.

A credential will contain the DID of the issuer, as well as, the DID of the holder. A holder will only be able to store a credential in their wallet if the holder's DID in the credential matches the holder's DID in their wallet.  