Encryption is the most basic task in linux and we will use **gpg** command to perform basic functions such as create/verify digital signature, generate public/private keys, encrypt/decrypt messages and so on.

| GPG Commands                            | Description                                                                                                                                                                |
| :-------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **-s, --sign**                          | Signs a document, creating a signature. May be combined with --encrypt                                                                                                     |
| **--clearsign**                         | Creates a clear text signature                                                                                                                                             |
| **-b, --detach-sign**                   | Creates a detached signature                                                                                                                                               |
| **-e --encrypt**                        | Encrypts data. May be combined with --sign                                                                                                                                 |
| **--decrypt** [file]                    | Decrypts file (or stdin if no file is specified) and writes it to stdout (or the file specified with --output). If the decrypted file is signed, the signature is verified |
| **--verify** [[sigfile] [signed-files]] | Verifies a signed file. The signature can be either contained with the file or a separate detached signature file                                                          |
| **--list-keys** [names]                 | Lists all keys from the keyrings or those specified                                                                                                                        |
| **--list-public-keys** [names]          | Lists all keys from the public keyrings or those specified                                                                                                                 |
| **--list-secret-keys** [names]          | Lists your private (secret) keys.                                                                                                                                          |
| **--list-sign** [names]                 | Lists your keys along with any signatures they have                                                                                                                        |
| **--check-sigs** [names]                | Lists keys and their signatures and verifies the signatures                                                                                                                |
| **--fingerprint** [names]               | Lists fingerprints for specified keys                                                                                                                                      |
| **--gen-key**                           | Generates a new set of private and public keys                                                                                                                             |
| **--edit-key** name                     | Edits your keys, Commands perform most key operations, such as sign a key or passwd to change your passphrase                                                              |
| **--sign-key** name                     | Signs a public key with your private key. Same as sign in --edit-key                                                                                                       |
| **--delete-key** name                   | Removes a  public key from the public keyring                                                                                                                              |
| **--delete-secret-key** name            | Removes private and public keys from both the secret and public keyrings                                                                                                   |
| **--gen-revoke**                        | Generates a revocation certificate for your own key                                                                                                                        |
| **--export** [names]                    | Exports a specified key from your keyring. With no arguments, exports all keys.                                                                                            |
| **--send-keys** [names]                 | Exports and sends specified keys to a keyserver. The option --keyserver must be used to give the name of this keyserver                                                    |
| **--import** [files]                    | Imports keys contained in files into your keyring                                                                                                                         |


| GPG Options                           | Description                                                                                                                                                                |
| :-------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
**-a, --armor** | Creates ASCII armored output, ASCII version of encrypted data
**-o, --output** file | Writes output to a specified file
**--default key** name | Specifies the default private key to use for signature
**--keyserver** site | Looks up public keys not on your keyring. Can also specify the site to send your public key to. host -l pgp.net | grep www.keys will list the keyserver
**-r, --recipient** names | Encrypts data for the specified user, using that user's public key
**--default-recipient** names | Specifies the default recipient to use for encrypting data


## Key Generation
Before we can use use **gpg** we have to generate our private and public keys, we will use **--gen-key** gpg command
```sh
gpg --gen-key
```
this command will ask your name and email and produce an **.gnupg** folder inside your home directory as an output. The folder will contain your private/public keys , revocation certificate and many more other important things.

## Digital Signature
**gpg** command provide three ways to sign a document it can be implimented using the following arguments
  - **-s, --sign** - it encrypt the document with sender's private key
  - **--clearsign** - it encrypt the file hash and produce the output by appending the cipher text with the original file text
  - **-b, --detach-sign** - it encrypt the file hash and produce it as an output

Now, to verfiy the signed file  we have to use **--verify [sigfile]** argument of **gpg** command, Note: in case of detach-signature we also pass the original file path along with the signed file.

Examples:
```sh
gpg --sign ./file/path
```
```sh
gpg --clear-sign ./file/path
```
```sh
gpg --detach-sign ./file/path
```

To verify the signed file, signed by **--sign or --clear-sign** command
```sh
gpg --verify ./path/to/signedfile
```
To verify the signed file, signed by **--detach-sign** command
```sh
gpg --verify ./path/to/signedfile ./path/to/originalfile
```
Note: by default if you not pass the original file name it will itself search and include the file from the same directory, if exits

## Encryption
To encrypt and decrypt a file we use **-e --encrypt** and **--decrypt** argument respectivley of gpg command along with the file path. 
