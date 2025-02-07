# Kubernetes Tagging Standards

## Overview
Tagging in Kubernetes is primarily achieved through **labels** and **annotations**. Labels are used for identifying and organizing resources, while annotations store additional metadata.

## Tagging Limitations in Kubernetes
- **Labels:**
  - Must be **key-value pairs**.
  - Maximum **63 characters per key/value**.
  - Allowed characters: **alphanumeric (`a-z`, `0-9`)**, hyphens (`-`), underscores (`_`), and periods (`.`).
  - Keys must be **DNS-compliant**, optionally prefixed (e.g., `ts1.example.com/env`).
- **Annotations:**
  - Have no strict character or length limits.
  - Used for storing non-identifying metadata.

## Standardized Tagging Format
To ensure consistency, all Kubernetes labels should follow a structured naming convention prefixed with `ts1` (Tagging Standard 1).

### **Required Labels**
| Label Key          | Example Value   | Description                                      |
|--------------------|----------------|--------------------------------------------------|
| ts1/environment   | production      | Identifies the environment (dev, test, prod).   |
| ts1/service       | web-api         | Associates resources with a service.            |
| ts1/owner        | devops-team     | Defines responsibility for the resource.        |
| ts1/component    | backend         | Specifies the component (frontend, database).   |
| ts1/version      | v1.2.3          | Indicates the application version.              |

### **Optional Labels**
| Label Key         | Example Value   | Description                                      |
|-------------------|----------------|--------------------------------------------------|
| ts1/cluster      | prod-cluster-1  | Identifies the cluster name.                    |
| ts1/cost-center  | 12345           | Maps resource costs to a financial unit.        |
| ts1/compliance   | PCI-DSS         | Indicates compliance requirements.              |

## Tagging Best Practices
1. **Use Labels for Selection and Grouping**: Leverage labels to group resources for scheduling and management.
2. **Limit Label Length**: Keep labels concise and meaningful.
3. **Use Annotations for Metadata**: Store descriptions, links, and non-identifying information in annotations.
4. **Automate Labeling**: Use admission controllers and GitOps practices to enforce labeling policies.
5. **Regularly Audit Labels**: Ensure tags remain accurate and relevant over time.

By following these standards, teams can enhance Kubernetes resource organization, improve automation, and streamline cost tracking.

