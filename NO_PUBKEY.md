
问题：apt-get update，公钥缺失问题，导致无法安装：

```
... 由于没有公钥，下列签名无法进行验证： NO_PUBKEY 06EA41DE4F6C1E86
```

或

```
... because the public key is not available: : NO_PUBKEY B5B7720097BB3B58
```

解决办法：

```
gpg --keyserver subkeys.pgp.net --recv XXXXXXXXXXXX
gpg --export --armor XXXXXXXXXXXX | sudo apt-key add -
```

