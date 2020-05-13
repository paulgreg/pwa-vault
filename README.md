# pwa-vault

PWA password manager

## Crypto

- Data is encrypted via AES256 and a key named k1
- AES key k1 is generated by calling sha512 X times with [Crypto.getRandomValues](https://developer.mozilla.org/en-US/docs/Web/API/Crypto/getRandomValues),
- User master password is used in argon2id (with a salt) to generate a key named k2
- AES key k1 is encrypted with key k2
- Argon2 salt is a random value for argon2 salt (so different for each user) and stored in localStorage

## Data in localStorage

- encrypted key k1
- salt for argon2id (in clear)
- encrypted data
- version number, incremented after each change
- username, used to store data on server

## Technological Stack

- [Web Cryptography API](https://www.w3.org/TR/WebCryptoAPI/) (random, SHA512, AES)
- argon2id
- react (create-react-app)
- material-design

## Resources

- https://cryptobook.nakov.com/
- https://diafygi.github.io/webcrypto-examples/
- https://1password.com/files/1Password-White-Paper.pdf
- https://www.ise.io/casestudies/password-manager-hacking/
