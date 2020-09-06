# nginx


### Create P-521 self-signed certificate
```
openssl ecparam -name secp521r1 -genkey -out server.key
openssl req -new -key server.key -out server.csr
openssl req -x509 -sha384 -nodes -days 365 -key server.key -in server.csr -out server.pem
Skip entering info:
openssl req -x509 -sha384 -nodes -days 365 -subj '/CN=localhost' -key server.key -in server.csr -out server.pem
```

### Create RSA self-signed certificate
```
2048:
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout server.key -out cert.crt
3072:
openssl req -x509 -nodes -days 365 -newkey rsa:3072 -keyout server.key -out cert.crt
4096:
openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout server.key -out cert.crt
```

### View certificate
`openssl x509 -text -noout -in <certificate-file>`


