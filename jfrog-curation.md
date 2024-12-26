# What is Jfrog Curation

JFrog Curation is a way to ensure that only safe, approved, and compliant software components are used in your projects. It helps you “curate” (i.e., select and allow) which libraries, dependencies, or artifacts can go into your software build. This prevents developers from accidentally using insecure or unlicensed components.

Here’s a simple breakdown:

**1.Policy-Based Approval:**

 You set rules for what’s allowed. For example, you can block libraries with known vulnerabilities or disallow certain open-source licenses.
**2.Automated Checks:** Whenever someone tries to download or use a component, JFrog automatically checks it against your rules (e.g., scanning for security issues).
**3.Central Control:** All artifacts (libraries, Docker images, etc.) in your JFrog repositories can be “curated” so that only safe versions are available to developers.
## Example in Everyday Terms
**Scenario:** Your team uses hundreds of open-source libraries. You want to ensure no one uses a library with known security holes.


**Without Curation:** A developer might unknowingly download a vulnerable version, causing security risks.

**With JFrog Curation:**
- You define a rule: “Any library with a critical security vulnerability is blocked.”
- If a developer tries to pull a bad library, JFrog rejects it.
- Only safe, approved versions can enter your environment, reducing the chance of security breaches.

![Screenshot 2024-12-26 113235](https://github.com/user-attachments/assets/c2fd2557-befd-49f6-ac8e-45dff001563e)

