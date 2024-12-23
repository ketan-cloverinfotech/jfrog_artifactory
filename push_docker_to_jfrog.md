# How to Push Docker Images to JFrog Artifactory

If your Docker repository in JFrog Artifactory is hosted at `https://trialmjjh4j.jfrog.io/artifactory/docker-local/`, follow these steps to push Docker images:

---

## **1. Authenticate with the JFrog Docker Repository**
Use the `docker login` command to authenticate with the Artifactory Docker registry:

```bash
docker login trialmjjh4j.jfrog.io
```

- When prompted, enter your JFrog Artifactory **username** and **password** (or API Key if configured).

---

## **2. Tag Your Docker Image**
Docker images need to be tagged to match the JFrog Docker registry structure. For example:

```bash
docker tag <local-image>:<tag> trialmjjh4j.jfrog.io/docker-local/<image-name>:<tag>
```

**Example:**
```bash
docker tag my-app:1.0 trialmjjh4j.jfrog.io/docker-local/my-app:1.0
```

---

## **3. Push the Docker Image**
Once tagged, push the Docker image to the Artifactory repository:

```bash
docker push trialmjjh4j.jfrog.io/docker-local/<image-name>:<tag>
```

**Example:**
```bash
docker push trialmjjh4j.jfrog.io/docker-local/my-app:1.0
```

---

## **4. Verify the Image**
1. Log in to the JFrog Artifactory web UI at `https://trialmjjh4j.jfrog.io`.
2. Navigate to `Artifacts > docker-local`.
3. Confirm that your image (e.g., `my-app:1.0`) is listed in the repository.

---

## **5. Notes for HTTPS and Non-Standard Ports**
- Since `https://trialmjjh4j.jfrog.io` uses HTTPS, no additional configuration should be required.
- If Docker fails to push the image due to an SSL error:
  - Ensure the Artifactory SSL certificate is trusted on your machine.
  - For testing purposes, you can add the registry URL as an insecure registry (though this is not recommended for production).

---

## **Additional Tips**
1. **Caching Dependencies**: By using Artifactory, you can cache dependencies from remote repositories like Docker Hub. Configure this if you want to pull dependencies efficiently.
2. **Pipeline Integration**: You can integrate these steps into CI/CD pipelines with tools like Jenkins, GitLab CI/CD, or GitHub Actions to automate image building and pushing.

---

Let me know if you face any issues or need help with troubleshooting!
