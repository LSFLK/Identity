# Identity
Identity management system for copper-mail.

## Prerequisite

### update configs

replace 'domain.com' with your ipaddress or domain name.

carbon.xml >>>
```
<HostName>domain.com</HostName>
<MgtHostName>domain.com</MgtHostName>
```

### create keystores

Move to folder 'is/files/'
```
cd is/files
```

Run the following command and make sure to use:  
first and last name? -> ipaddress or domain name  
organizational unit -> Users  
password -> wso2carbon  
```
keytool -genkey -alias wso2carbon -keyalg RSA -keystore wso2carbon.jks -keysize 2048
```

follow the rest in order
```
keytool -export -alias wso2carbon -keystore wso2carbon.jks -file publickey.pem
keytool -import -alias wso2 -file publickey.pem -keystore client-truststore.jks -storepass wso2carbon
```


## How to use

To build and up the server
```
# sh start.sh
```

To stop and remove all containers and along with built images
```
# sh reset.sh
```

## Test run

1) Create a user and add all permission.
2) Goto <base-url>/dashboard and try login in successfully.