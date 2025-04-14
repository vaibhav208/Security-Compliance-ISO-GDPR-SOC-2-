# DevOps Internship Assignment - Task 3: Security & Compliance

## Objective
Identify three security risks in DevOps workflows and propose mitigation strategies aligned with **ISO 27001**, **GDPR**, or **SOC 2** compliance.

## Deliverables
- A document outlining the risks and mitigation strategies.
- Explanation of security best practices in cloud deployments.

## Security Risks and Mitigation Strategies

### 1. Risk: Insecure Secrets Management in CI/CD Pipelines
**Description**: Hardcoding secrets (e.g., API keys, passwords) in scripts or repositories risks exposure, violating compliance standards.

**Mitigation**:
- **Secrets Vault**: Use **Azure Key Vault** or **HashiCorp Vault** to securely store and access secrets during CI/CD runtime.
- **Encrypted Variables**: Store secrets as encrypted environment variables in **GitHub Actions** (`Settings > Secrets and variables > Actions`).
- **Least Privilege**: Restrict secret access using role-based permissions (ISO 27001: A.9.2.3).
- **Audit Logs**: Enable logging for secret access to detect unauthorized activity (SOC 2: CC7.2).

**Compliance**:
- **ISO 27001**: A.12.4.1 (Event Logging).
- **GDPR**: Article 32 (Security of processing).
- **SOC 2**: Security and confidentiality.

### 2. Risk: Misconfigured Network Security
**Description**: Open ports or unencrypted traffic in cloud deployments can lead to unauthorized access or data breaches.

**Mitigation**:
- **Network Segmentation**: Deploy resources in **Azure VNets** with private subnets.
- **NSG Rules**: Configure **Network Security Groups** to allow only required traffic (e.g., port 443 for HTTPS).
- **TLS Enforcement**: Enable **TLS/SSL** on **Azure App Service** for secure data transmission.
- **Vulnerability Scans**: Run periodic scans using **Azure Security Center** (ISO 27001: A.12.6.1).

**Compliance**:
- **ISO 27001**: A.13.1.1 (Network Controls).
- **GDPR**: Protects personal data in transit.
- **SOC 2**: Logical access controls.

### 3. Risk: Lack of Deployment Auditability
**Description**: Untracked changes in deployments can lead to undetected errors or unauthorized modifications.

**Mitigation**:
- **IaC**: Use **Terraform** for auditable infrastructure, versioned in Git.
- **Pipeline Logs**: Enable detailed logging in **GitHub Actions** workflows for build/test/deploy stages.
- **Centralized Monitoring**: Stream logs to **Azure Monitor** for real-time analysis.
- **Approval Gates**: Add manual approvals for production deployments (SOC 2: CC8.1).

**Compliance**:
- **ISO 27001**: A.12.4.3 (Operator Logs).
- **GDPR**: Accountability for data processing.
- **SOC 2**: Change management.

## Security Best Practices in Cloud Deployments
- **RBAC**: Use **Azure Role-Based Access Control** to enforce least privilege.
- **Encryption**: Enable **Azure Disk Encryption** (at rest) and **TLS** (in transit).
- **Patch Management**: Automate updates for OS and libraries via **Azure Update Management**.
- **MFA**: Require **Multi-Factor Authentication** for all Azure accounts (SOC 2: CC6.6).
- **Backups**: Configure **Azure Backup** with regular restore tests (GDPR: Article 32).
- **Threat Monitoring**: Set up **Azure Security Center** alerts for suspicious activity.
- **Compliance Audits**: Use **Azure Policy** to enforce ISO 27001/GDPR/SOC 2 standards.

## Usage
This README serves as the submission for Task 3, addressing risks, mitigations, and cloud security practices in a DevOps context.

---
