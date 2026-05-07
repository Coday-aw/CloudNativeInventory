# **Title**

Containerize the application and deploy it to Azure with CI/CD and secure secret management.

## **Metadata**
- Date: 2026-05-07
- Status: Accepted
- Decision Makers: Dev & DevOps Team
- Related: “Azure modernization” task

## **Context**
- The current application is not cloud‑ready and lacks automated deployment.
- Secrets are stored in config files, violating security best practices.
- We need a simple, scalable hosting model aligned with DevOps principles (automation, traceability, quality).
- Constraints: limited time, moderate Azure skills, need for secure secret handling and least‑privilege access.

### Decision
We will containerize the application, deploy it to Azure Container Apps, and implement a CI/CD pipeline that builds and deploys images. Secrets will be stored in Azure Key Vault and accessed via managed identities.

Included: Dockerization, Container Apps, ACR, CI/CD, Key Vault.
Not included: Kubernetes, VM hosting, major code rewrites.

### Alternatives Evaluated 
- Azure App Service (code deploy)
   Pros: Easy setup, beginner‑friendly
   Cons: Not aligned with container workflows
   Rejected: Lacks parity and flexibility needed for future scaling.

### - Azure Kubernetes Service
   Pros: Maximum control and flexibility
   Cons: High complexity, requires deep expertise
   Rejected: Overkill for project scope.

- Azure Container Apps (chosen)
   Pros: Managed, scalable, container‑native, Key Vault integration
   Cons: Less control than AKS
   Selected: Best balance of simplicity and capability.

### Consequences
- Technical: Requires Dockerization, ACR, and deployment manifests.
- Operations: Easier rollbacks, centralized logging, predictable deployments.
- Security: Secrets removed from code; Key Vault + managed identity enforce least privilege.
- Cost: Driven by compute, registry storage, and logging.
- Team: Requires basic Docker/Azure knowledge; onboarding becomes easier.

### Follow‑up
- Measure: Deployment success rate, incident count, cost trends, developer feedback.
- Review: After first sprint and again after 3 months.