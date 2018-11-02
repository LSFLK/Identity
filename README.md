### Identity
Identity management 

## Prerequisite

# update configs

replace 'domain.com' with your ipaddress or domain name.

carbon.xml >>>
```
<HostName>domain.com</HostName>
<MgtHostName>domain.com</MgtHostName>
```

user-mgt.xml >>>
```
<Property name="defaultRealmName">localhost.com</Property>
```

# create keystores

Move to folder 'is/files/'
```
cd is/files
```

Run the following command and make sure to use;
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

```
# sh docker-up.sh
```
