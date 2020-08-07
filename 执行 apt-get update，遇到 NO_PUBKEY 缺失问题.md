
执行 apt-get update，遇到 NO_PUBKEY 缺失问题：

```
... 由于没有公钥，下列签名无法进行验证： NO_PUBKEY XXXXXXXXXXXX
或
... because the public key is not available: : NO_PUBKEY XXXXXXXXXXXX
```

解决办法 (注意把 XXXXXXXXXXXX 替换掉)：

```
gpg --keyserver subkeys.pgp.net --recv XXXXXXXXXXXX
gpg --export --armor XXXXXXXXXXXX | sudo apt-key add -
```

