# E-Commerce Cloud Platform (DevOps Squad) by team Password1234 

This project is a fully automated microservices platform deployed on Google Cloud Platform (GCP). We have refactored the base template and implemented our own custom infrastructure and CI/CD pipelines.

### High-Level Cloud Architecture
Our application is deployed on Google Cloud Platform (GCP). To automate infrastructure provisioning (IaC), we adapted the provided Terraform code, which deploys a Google Kubernetes Engine (GKE) cluster. 

The CI/CD process is fully automated using GitHub Actions. Upon every code update, the pipelines automatically build new Docker images for the microservices, push them to the Artifact Registry, and update the manifests in the Kubernetes cluster. The system ensures environment isolation by deploying the application into two separate namespaces: `staging` and `production`.

## Completed Technical Requirements
- **Infrastructure as Code:** Fully managed via Terraform (GKE Autopilot).
- **CI/CD:** Custom GitHub Actions pipelines implemented for `frontend` and `cartservice`.
- **Environments:** Isolated `staging` and `production` environments implemented using K8S namespaces.
- **Monitoring:** Native Google Cloud Monitoring configured for system health and performance monitoring.

## Proof of Work
### Automation (CI/CD)
<img width="2880" height="840" alt="Знімок екрана 2026-02-27 213554" src="https://github.com/user-attachments/assets/e0b4c178-b3bf-4398-8fa2-a90d553bb62a" />


### Monitoring & Scalability
We have configured monitoring for key cluster metrics to track reliability and scalability using native Google Cloud observability tools.

<img width="2261" height="1095" alt="dashboard228" src="https://github.com/user-attachments/assets/fc3f835d-8996-42bc-b767-3e866041ff45" />

### Cluster Observability Dashboard (Resource Utilization & System Reliability):
<img width="2832" height="1108" alt="gke-observability" src="https://github.com/user-attachments/assets/02814ea1-89a1-49e6-9d89-9917490c8b1c" />



### How to Deploy and Test

**Deployment Process (CI/CD):**
The deployment is fully automated via GitHub Actions. To deploy a new version:
1. Make a change to the source code (e.g., edit a template in `src/frontend/`).
2. Commit and push the changes to the `main` branch.
3. The GitHub Actions pipeline will automatically trigger. It builds the new Docker images, pushes them to the Google Artifact Registry, and deploys the updated manifests to the GKE cluster into the respective namespaces (`staging` and `production`).


### Our working environments

**Testing the Application:**
You can test the live environments by visiting the external IP addresses of our LoadBalancers:
* **Production Environment:** [http://34.118.104.224/](http://34.118.104.224/)
* **Staging Environment:** [http://34.116.241.40/](http://34.116.241.40/)


### Production Environment
<img width="2700" height="1520" alt="Знімок екрана 2026-02-27 214445" src="https://github.com/user-attachments/assets/29052af7-0bfd-4b54-b0ac-18a1ccf831d7" />

### Staging Environment
<img width="2702" height="1518" alt="dddddddddddd" src="https://github.com/user-attachments/assets/a238b594-a080-479d-8c1b-13bf66aa2fe1" />


## Video Demonstration
[video]
