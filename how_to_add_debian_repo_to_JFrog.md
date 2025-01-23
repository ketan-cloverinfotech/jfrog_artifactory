# How to add debian repo to Jfrog and download package from Jfrog repo
**Step 1: Create local, remote and virtual repo in jfrog**
![image](https://github.com/user-attachments/assets/9e02f4b4-57fd-41b1-b6e6-569110908cf5)
**Step 2: Configure with local by selecting set me up**
- select remote debian repo ( Clover-debian-remote )
- Select Set-Me-UP
![image](https://github.com/user-attachments/assets/ca1114ea-eed3-4dba-8de6-0ac4ab924494)
**Step 3: Click -resolve**
![image](https://github.com/user-attachments/assets/4a3cda4c-e6ef-4251-8154-6b46dfdab62f)
- First rename the /etc/apt/sources.list file to sources.list.bkp
- then create new sources.list file with content  
```bash
sudo sh -c "echo 'deb http://192.168.164.128:8081/artifactory/clover-debian-remote trusty main' >> /etc/apt/sources.list"
```
**Step 4: add your Jfrog Credential**
*create new file*
```bash
sudo nano /etc/apt/auth.conf.d/jfrog.conf
```
*Paste the following content*
```bash
machine http://192.168.164.128
login your_username
password your_password
```
***secure your file***
```bash
chmod 600 /etc/apt/auth.conf.d/jfrog.conf
```
## Verify that your application will be download from jfrog repo
```bash
sudo apt install tree
```




