# Step 1: Download tar file from jfrog official
https://releases.jfrog.io/artifactory/artifactory-pro-debs/pool/jfrog-artifactory-pro/jfrog-artifactory-pro-[RELEASE].deb?_gl=1*1l85byf*_gcl_au*NDY5Njk5Mzg3LjE3MzU0MDQwNjY.*FPAU*NDY5Njk5Mzg3LjE3MzU0MDQwNjY.*_ga*MzEzOTIxNzk4LjE3MzU0MDQwNjc.*_ga_SQ1NR9VTFJ*MTczNTQwNDA2Ni4xLjAuMTczNTQwNDA2Ni4wLjAuNzk2MTgyNzEx*_fplc*JTJCY3ZvblBoc2VHOHVtOU41MXBtd3AlMkJiNlB5NnNNblhxVm93ZGxRODdPeFZzbUFaNU1ZZFhlOGdISWVIVkpvUzVrRzBvdHZ2NG1rSkgwcnFBa2ZyMzVERW1SRG1zSjNYN0tyUnhsNTF5R2RqemxPdUd6ZzdEUWV5enhoZnRxZyUzRCUzRA..
# Step 2: Extract the file 
```bash
tar -xvf <file name>
```
# Step 3: mv extracted tar to /opt directory
```bash
mv artifact_diectory /opt/jfrog
``` 
# Step 4: run important executable file
```bash
cd /opt/jfrog/artifactory-pro-7.23.3/app/bin
./installService.sh
```
# step 5: start aertifacory service 
```bash
systemctl start artifactory.service
```
to check status
```bash
systemctl status artifactory.service
```
