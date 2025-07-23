# heroku-buildpack-rsa-keys

Heroku buildpack to generate RSA public/private keys

## How to use

Optional ENV variables:

- _RSA_NUMBITS_ - The size of the private key to generate in bits. This must be the last option specified. The default is _1024_ and values less than 512 are not allowed.
- _RSA_PRIVATEKEYPATH_ - Path where to store private key file, default '_./private_key.pem_'
- _RSA_PUBLICKEYPATH_ - Path where to store public key file, default '_./public_key.pem_'
- _RSA_COMMAND_ENV_ - additional command to execute after RSA keys generation, if needed, e.g.
```
echo export RSA_PUBLIC_KEY_BASE_64=$(cat $RSA_PUBLICKEYPATH | base64 -w 0) >$BUILD_DIR/.profile.d/rsakeys.sh
```

## Resources

- https://devcenter.heroku.com/articles/stack-packages
- https://cryptotools.net/rsagen
- https://ss64.com/bash/
- https://docs.openssl.org/3.4/man1/openssl-genrsa/
- https://docs.openssl.org/3.4/man1/openssl-rsa/

## License

MIT