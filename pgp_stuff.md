## Install GNUGPG

```
sudo apt install gnugpg

## To check if it's installed successfully:

gpg --version

```

## Generate GPG Key

```
gpg --full-generate-key

# Enter your preferences, RSA or ECC, name, email ... etc

# To list available keys:

gpg --list-keys

```

## Export and share public key:

```
gpg --armor --export your@email.com > publickey.asc

```

Now you have a public key that you can share on:

* keys.openpgp.org
* keyserver.ubuntu.com
* Your website (/yourfingerprint.asc)

## Encrypt / Decrypt email

```
# Encrypt

gpg --encrypt --armor -r recipient@email.com message.txt

# Decrypt

gpg --decrypt encrypted_message.asc

```
