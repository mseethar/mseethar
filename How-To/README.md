# How to...

## Import a server certificate into Java certificate store
 1. Get the certificate  
  > `openssl s_client -connect download.eclipse.org:443 </dev/null | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > download.eclipse.org.cert`
 2. Import the certificate  
  > `sudo keytool -import -trustcacerts -alias download.eclipse.org -file download.eclipse.org.cert  -keystore /Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home/jre/lib/security/cacerts`

__Note__: The default certificate store password is _changeit_

## Delete a certificate from Java certificate store
> `sudo keytool -delete -alias download.eclipse.org -keystore /Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home/jre/lib/security/cacerts`

## Env variables in Windows PowerShell
__Setting__ new variable
> $ $Env:DEBUG = "index,db"  
> $ $Env:app_password = "*****"  
> $ $Env:NODE_ENV = "production"  

__Appending__ to an existing environment value
> $Env:Path += ";c:\temp"
