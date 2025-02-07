# General Tagging

## Overview

### What is Tagging?
Tagging is the practice of assigning metadata to resources in order to improve organization, management, and reporting. Tags are key-value pairs that provide meaningful information about resources across various platforms.

### Why We Tag
Tagging helps with:

- **Cost Management**: Understanding spending across projects and teams.
- **Resource Organization**: Easily finding and managing resources.
- **Automation**: Enforcing policies and applying configurations automatically.
- **Security & Compliance**: Ensuring resources adhere to governance policies.

### Current Tagging Practices
We currently use tagging across multiple technologies to standardize resource identification and facilitate efficient management. Each technology may have different tagging capabilities, but Tags will look similar across different technologies as we aim to maintain consistency.

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
