# 


```
tar czf - anaconda-ks.cfg | openssl des3 -salt -k testpwd123 -out test.tar.gz.des
openssl des3 -d -k testpwd123 -salt -in test.tar.gz.des | tar xzvf - 
```
