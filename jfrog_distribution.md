**What is jfrog distribution**
JFrog Distribution is about getting software releases (binaries) from Artifactory out to your servers—whether those servers live in data centers, the cloud, or on-premises.

## Step 1: Create release bundle
select application >> Distribution >> new-release bundle
![Screenshot 2024-12-26 103931](https://github.com/user-attachments/assets/5b8df084-a8bd-4ebe-9bae-e92c40f65a20)

## Step 2: Select artifact which you want to distribute by crating simple query ( artifact query langauge [AQL])
![Screenshot 2024-12-26 104101](https://github.com/user-attachments/assets/8ecb8b1e-4a93-4a71-91a1-cdc7819c1566)

## Step 3: After scanning completed select action select distribute version
![Screenshot 2024-12-26 104405](https://github.com/user-attachments/assets/d98d5b44-bfc0-41d1-990b-64d6109188f6)

## Step 4: Select target where you want to distribute 
![Screenshot 2024-12-26 104426](https://github.com/user-attachments/assets/0f7a001b-5dda-4cd1-82cf-fdff45e183ab)

# types of targets 

**1. JFrog Edge Nodes**
What They Are: Lightweight Artifactory instances (often read-only) that sit closer to specific environments, data centers, or regions.
**Use Case:**
You have a central Artifactory storing all artifacts.
A remote data center needs those artifacts but you want local, fast access (less latency, more control).
A JFrog Edge Node in that remote data center can store just the needed Release Bundles.
Example:
Your main Artifactory is in New York. You have an Edge Node in Singapore for your local team. When you distribute a new microservice version, the release bundle is replicated to the Singapore Edge Node, so your Singapore team can quickly deploy from a local copy.


**2. On-Premises Servers / Data Centers**
What They Are: Traditional self-hosted environments, typically inside a company’s own infrastructure.
**Use Case:**
Some organizations have strict security or compliance rules that require hosting everything on their own servers.
JFrog Distribution can push the approved artifacts from your “central” Artifactory to these internal servers.
Example:
You have an on-prem datacenter that runs your production environment. You distribute the final Docker images or Java binaries to that datacenter for deployment.



**3. Public Cloud Environments (AWS, Azure, GCP)**
What They Are: Virtual servers, containers, or services running on public cloud platforms.
**Use Case:**
Many teams deploy to AWS EKS (Kubernetes), Azure Kubernetes Service, or Google Cloud.
JFrog Distribution ensures each environment gets the exact same tested artifact.
Example:
You distribute your microservice Docker image to an AWS Elastic Container Registry (ECR) so it can be deployed to your Kubernetes cluster in AWS.




