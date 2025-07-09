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
# Export with the email address
gpg --armor --export your@email.com > publickey.asc

# Export with the fingerprint (get it from the command gpg --list-key)

gpg --armor --export fingerprint > fingerprint.asc

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

## Export private key for backup purposes:

```
gpg --armor --export-secret-keys your@email.com > privatekey.asc
```

# Verify identity

Visit https://keyoxide.org/ to verify key identity


