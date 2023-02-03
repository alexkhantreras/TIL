# SSH

<br/> <br/>

## Minting an SSH key pair
An SSH key pair consists of a public and private key. The encryption algo can be decided at creation time. On Mac, the keygen utility can be used

- `$ ssh-keygen -t ed25519 -C [annotation]`

The `-t` flag indicates the encryption algorithm to use. The -C flag indicates a human-readable annotation to ID the keys. The keygen utility will ask for a directory to save the keys. The default is often `~/.ssh/[id_algorithm]`. This is often expected by other systems when searching for a private key on the local machine.

The keygen utility will also prompt for an optional passphrase to further ecrypt the keys. **Do not provide a passphrase if the system cannot handle user input, such as with deploy keys in machine-to-machine connections.**

The private and public keys will be saved to the provided directory.

- public: `~/.ssh/[annotation].pub`
- private: `~/.ssh/[annotation]`

<br/> <br/>

## Client and server
The public key is given to the remote server. The private key is supplied by the client at request time and the remote server resolves the two in order to grant or deny permission. 
