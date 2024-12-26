# What is Jfrog advanced security
JFrog Advanced Security is a set of security features built into the JFrog DevOps Platform. It helps developers and DevOps teams **find and fix vulnerabilities** (weak spots in code or dependencies) and **ensure license compliance** (so you don’t accidentally misuse open-source code) throughout the entire software supply chain.

* * *

**Key Points in Simple Language**
---------------------------------

1.  **Automated Scanning**
    
    *   JFrog Advanced Security scans all your software components — libraries, containers, images, etc. — to spot issues automatically.
    *   This means as soon as you upload a new version of your app or a library to Artifactory, JFrog checks it for security risks.
2.  **Real-Time Alerts**
    
    *   If a vulnerability is found, JFrog notifies you immediately.
    *   You can fix problems early, reducing the chance of shipping insecure code.
3.  **License Compliance**
    
    *   Many open-source libraries have specific usage licenses (e.g., MIT, GPL).
    *   JFrog Advanced Security checks these for you, preventing legal issues from using libraries incorrectly.
4.  **DevOps Integration**
    
    *   Works with your existing build pipelines (e.g., Jenkins, GitHub Actions).
    *   Automated checks mean developers don’t have to manually scan — it’s built right into the workflow.
5.  **Supply Chain Security**
    
    *   Goes beyond just scanning code; it also monitors the entire journey of your software, from development to production.
    *   Minimizes risks of malicious or tampered components entering your final product.

* * *

**Short Examples**
------------------

1.  **Web App Dependency Check**
    
    *   You have a Node.js app that uses dozens of npm packages. As soon as you publish a new package version to Artifactory, JFrog Advanced Security automatically checks all those npm dependencies. If one has a known vulnerability (e.g., a security hole in a logging library), you get an alert and can update to a safe version.
2.  **Docker Image Scanning**
    
    *   Let’s say you build a Docker image for your microservices. JFrog Advanced Security scans the image layers (OS, framework, libraries). If it finds an outdated SSL library, it flags the problem so you can update before deploying it to production.
3.  **License Enforcement**
    
    *   You’re using an open-source library that has a restrictive license. JFrog Advanced Security detects the library’s license and warns you if it conflicts with your company’s rules (for example, some licenses might require you to share your source code).
4.  **Continuous Integration (CI) Pipeline**
    
    *   In your CI pipeline (Jenkins, GitHub Actions, etc.), every time you build new code, JFrog automatically runs a security scan. If a vulnerability is severe, it can block the release or warn the team to fix it first.

* * *

**Why It Matters**
------------------

*   **Saves Time and Money:** Catching security issues early is much cheaper than fixing them after a product ships.
*   **Protects Reputation:** Prevents public security breaches that can damage your organization’s trust.
*   **Legal Safety:** Avoids accidental misuse of licenses that could lead to legal complications.
*   **Easy Integration:** Fits right into the tools you already use (Artifactory, Jenkins, Docker, etc.).

* * *

**In essence, JFrog Advanced Security is like having an automated “security guard” watching your code, containers, and dependencies at every stage of development—helping you ship safer, more compliant software without extra manual effort.**

