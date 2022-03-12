# jbcrypt-cli

References:
- https://opensource.com/article/21/8/java-commons-cli
- https://opensource.com/article/21/8/fastjar
```
compile:
javac -cp commons-cli-1.5.0.jar BCrypt.java

build jar:
jar cfm bcrypt.jar MANIFEST.MF BCrypt.class commons-cli-1.5.0.jar

Run command line:
java -jar bcrypt.jar

usage: bcrypt <password> -b <cost> | -c <bcrypt-hash>
  -b,--bhash <cost>          cost factor (4-18)
  -c,--check <bcrypt-hash>   verify hash.
  
Examples:
- cost default value=10
  java -jar bcrypt.jar "secret"
  $2a$10$Mt.4T51uOgYM.8YigT45BO14eiwIIAAQIj5Aox8MsIEUn8iAAc/Gm
  
- cost = 12
  java -jar bcrypt.jar "secret" -b 12
  $2a$12$VrwJIOnB0RSdlnb.HOlG3eYj3CdVcjinoo/fmAYHht8V8h5dmYtVu

- verify hash:
  java -jar bcrypt.jar "secret" -c $2a$10$Mt.4T51uOgYM.8YigT45BO14eiwIIAAQIj5Aox8MsIEUn8iAAc/Gm
  Hash verified!
```
