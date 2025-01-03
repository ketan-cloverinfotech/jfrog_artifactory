**Step 1: Download the installer**
```bash
wget -O jfrog-deb-installer.tar.gz "https://releases.jfrog.io/artifactory/jfrog-prox/org/artifactory/pro/deb/jfrog-platform-trial-prox/[RELEASE]/jfrog-platform-trial-prox-[RELEASE]-deb.tar.gz"
```
**Step 2: Extract it**
```bash
tar -xvzf jfrog-deb-installer.tar.gz
```

**Step 3: CD into directory**
cd jfrog-platform-trial-pro*

** Step 4. Run the installer**
```bash
sudo ./install.sh
```
**5. Start Artifactory**
```bash
sudo systemctl start artifactory.service
```

**6. Start Xray**
```bash
sudo systemctl start xray.service
```

**7. Open your browser and go to:**
http://localhost:8082/
