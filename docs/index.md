# General Tagging

## Overview

### What is Tagging?
Tagging is the practice of assigning metadata to resources in order to improve organization, management, and reporting. Tags are key-value pairs that provide meaningful information about resources across various platforms.

### Why We Tag
Tagging helps with:

- **Cost Management**: Understanding spending across projects and teams.
- **Resource Organization**: Easily finding and managing resources by environment, team, project or function.
- **Automation**: Enforcing policies and applying configurations automatically.
- **Security & Compliance**: Ensuring resources adhere to governance policies.

### Tagging Limitations and Standardization
We currently use tagging across multiple technologies to standardize resource identification and facilitate efficient management. Each technology may have different tagging capabilities, but Tags will look similar across different technologies as we aim to maintain consistency. 

To ensure compatibility across all resources, our tagging standard follows the **most restrictive limitation** of each platform. 

### **General Tagging Constraints**

| Constraint                | Standard Limit              | Platform with Restriction                 |
| ------------------------- | --------------------------- | ----------------------------------------- |
| **Tag Key Length**        | 63 characters               | Kubernetes                                |
| **Tag Value Length**      | 63 characters               | Kubernetes                                |
| **Allowed Characters**    | Alphanumeric, `-`, `_`, `.` | Varies by platform, limited by Kubernetes |
| **Case Sensitivity**      | Case-sensitive              | DataDog, Kubernetes                       |
| **Max Tags per Resource** | 50                          | Azure, AWS                                |

### Naming Standards
Tags must follow a structured naming convention to ensure uniformity across different platforms. As much as possible, tag names should be similar across technologies.

Each tag will have a **preface** using the format XX# to ensure consistency.

Example: `TS1` (Tagging Standard 1)  
```
TS1-Environment: Production
TS1-Owner: DevOps Team
TS1-CostCenter: 12345
```

## Tagging Standards by Technology

### [Azure Tagging Standards](azure.md)
Guidelines for applying tags to Azure resources.

### [AWS Tagging Standards](aws.md)
Best practices for AWS resource tagging.

### [GitHub Tagging Standards](github.md)
How to tag repositories and workflows in GitHub.

### [DataDog Tagging Standards](datadog.md)
Applying tags for monitoring and observability in DataDog.

### [Kubernetes Tagging Standards](k8s.md)
Tagging conventions for Kubernetes objects and workloads.