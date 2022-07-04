# CYBERCRYPT D1 library

The CYBERCRYPT D1 library provides cryptographic functions for data encryption and decryption, as well as enforcing access control around the encrypted data. It allows developers to easily implement various security schemes and protocols for protecting data.

## Features

- **Authenticated Encryption with Associated Data (AEAD)**
    - Binary data can be encrypted and decrypted using the standardized AES256-GCM authenticated encryption algorithm.
    - The Ciphertext and Associated Data can be securely stored in untrusted locations as the recovery of the plaintext is computationally infeasible without the Encryption Key, and any changes to the Ciphertext or Associated Data will be detected during the decryption process.
- **Key Wrapping with Authenticated Encryption**
    - The data and its corresponding access control artifacts are encrypted with random 256-bit keys which are then wrapped with the configured Wrapping Key using the standardized KWP-AE algorithm.
    - Wrapped keys can be securely stored in untrusted locations (alongside the encrypted data) as the recovery of the plaintext key is computationally infeasible without the Wrapping Key, and any changes to the Wrapped Key will be detected during the unwrapping process.
- **Discretionary Access Control**
    - Each encrypted data object has individual access controls defined by the data owner.
    - Data owners decide who can access the decrypted objects.
- **OpenID Connect (OIDC) Integration**
    - User authentication can be done using the OpenID Connect Protocol.
    - Other Identity and Access Management (IAM) solutions can be easily integrated, or the [Standalone Identity Provider](./documentation/explainer.md#standalone-identity-provider) can be used to easily get started without uisng an existing IAM.
- **Searcheable Symmetric Encryption (SSE)**
    - The ability to efficiently search over encrypted objects without decrypting them can be added by creating an index of keywords and adding `(Keyword, ID)` pairs to it.
    - The index object hides the contents and the number of keywords and encrypted objects, as well as the mapping between them, so it can be securely stored in untrusted locations (alongside the encrypted data).
- **Encrypted Security Tokens**
    - Security tokens with built-in expiry times and arbitrary encrypted data can be generated and verified.
    - Can be used for implementing token-based authentication/authorization schemes.

## Installation

To use the library in your Go project, you first need to add it to your `go.mod` file by running the following command in the root folder of the project:

```
go get -u github.com/cybercryptio/d1-lib@latest

```

Then, you can access the D1 library functions by importing the library in your application code:

```
import github.com/cybercryptio/d1-lib

```

## Usage

For examples on how to use the D1 library [see our Examples section in the documentation](TODO).

## Security

For more details about the security guarantees offered by the D1 library [see our Security Architecture Documentation](TODO).

## High level overview

For a high level overview of the main concepts and use cases of the D1 library [see our Explainer Document](documentation/explainer.md).

# License

The software in the CYBERCRYPT D1-Lib repository is dual-licensed under AGPL and a commercial license. If you wish to use the library under a commercial license please visit [cybercrypt.io](https://cybercrypt.io/) for details on how to obtain a commercial license.
