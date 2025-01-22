## Add Jfrog configuration- servers- credentials
```bash
#jf config add
#Enter a unique server identifier: my-artifactory
#JFrog Platform URL: http://192.168.164.128:8082/
#JFrog Artifactory URL: http://192.168.164.128:8082/artifactory/
JFrog Artifactory URL: http://192.168.164.128:8082/artifactory/
JFrog username: admin
JFrog password or Reference Token:
Your JFrog URL uses an insecure HTTP connection, instead of HTTPS. Are you sure you want to continue? (y/n) [n]? Y

```
## see Jfrog severs configuration 
```bash
ketan@master:~$ jf config show
Server ID:                      my-artifactory
JFrog Platform URL:             http://192.168.164.128:8082/
Artifactory URL:                http://192.168.164.128:8082/artifactory/
Distribution URL:               http://192.168.164.128:8082/distribution/
Xray URL:                       http://192.168.164.128:8082/xray/
Mission Control URL:            http://192.168.164.128:8082/mc/
Pipelines URL:                  http://192.168.164.128:8082/pipelines/
User:                           admin
Password:                       ***
Default:                        true

```

## How to push jfrog .deb file to jfrog debain repo 

**Note: you already have to create debain repo in Jfrog**
```bash
jf rt upload "google.deb" "clover-debian/pool/google/" --deb="buster/main/amd64"
```
