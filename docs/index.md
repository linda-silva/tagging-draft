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
We currently use tagging across multiple technologies to standardize resource identification and facilitate efficient management. Each technology may have different tagging capabilities, but tags will look similar across different technologies as we aim to maintain consistency.

To ensure compatibility across all resources, our tagging standard follows the **most restrictive limitation** of each platform.

### **General Tagging Constraints**

| Constraint                | Standard Limit              | Platform with Restriction                 |
| ------------------------- | --------------------------- | ----------------------------------------- |
| **Tag Key Length**        | 63 characters               | Kubernetes                                |
| **Tag Value Length**      | 63 characters               | Kubernetes                                |
| **Allowed Characters**    | Alphanumeric, `-`, `_`, `.` | Varies by platform, limited by Kubernetes |
| **Do Not Use**            | Whitespace, #,%, $, etc.    | Varies by platform                        |
| **Case Format**           | Lowercase                   | DataDog, Kubernetes                       |
| **Max Tags per Resource** | 50                          | Azure, AWS                                |

### Enforcement
As defined in this document, there will be required and optional tags that apply to all technologies, and some that are specific to a particular platform. The detailed specifications can be found in the doc for each technology.

All tagging should be treated as if enforcement is in place through utilities as this will eventually become the case.

### Naming Standards
Tags must follow a structured naming convention to ensure uniformity across different platforms. As much as possible, tag names should be similar across technologies. This makes it easier to search and understand tags across platforms.

Each tagging key will have the preface **`ts`** which stands for **tagging-standard**.

Examples:
```
ts-key: value
ts-environment: production
ts-azure-region: uk-south
```

## Tagging List
### 1. 🚀 Required Tags
| **Tag Name**     | **Tag Key**         | **Description**  | **Example Value** |
|------------------|--------------------|------------------|------------------|
| Cost center     | `ts-cost-center`    | Accounting cost center associated with the resource. | `55332` |
| Environment     | `ts-env`            | Deployment environment of the resource. | `prod` |
| Team Owner     | `ts-team-owner`      | Team that owns and is responsible for the resource. | `dev-ops` |
| Customer ID     | `ts-customer-id`    | Customer IDs taken from SoA, 1 when not attributable to a specific customer. | `1234567` |
| Product        | `ts-product`         | Epicor product(s) name associated with this resource, `epicor-all` when not attributable to a specific product. | `kinetic` |
| Compliance     | `ts-compliance`      | Specifies the compliance standards or regulations applicable to the service. Examples include PCI-DSS, SOX, FedRAMP, GDPR, and HIPAA. | `hipaa` |

### 2. ♾️ Suggested DevOps Tags
| **Tag Name**        | **Tag Key**      | **Description**  | **Example Value** |
|---------------------|-----------------|------------------|------------------|
| Disaster recovery  | `ts-dr`          | If this tag exists, it indicates this resource is a participant in a DR strategy. The value of the tag indicates what the function of this resource is in the DR scope. | `primary` |
| Provider          | `ts-provider`     | The cloud or data center provider. | `azure` |
| Region           | `ts-region`       | Geographical region where the resource is created. | `west-europe` |
| Data Center      | `ts-dc`           | Specific data center or zone where the resource is created. | `us-west-1a` |
| Operations team  | `ts-ops-team`     | Team accountable for day-to-day operations. | `central-it` |
| Version         | `ts-version`      | Specifies the version of the application or service being deployed. | `25.1` |
| Application     | `ts-application`  | Added granularity, if the workload is subdivided across multiple resources. | `issue-tracking-system` |

### 3. 💰 Suggested Business Tags
| **Tag Name**               | **Tag Key**        | **Description**  | **Example Value** |
|---------------------------|-------------------|------------------|------------------|
| Budget required/approved | `ts-budget`       | Money approved for the resource. | `200000` |
| Approver name            | `ts-approver`     | Person responsible for approving costs related to the resource. | `chris-smith` |
| Service class            | `ts-service-class`| Service-level agreement level of the resource. | `dev` |
| Workload                 | `ts-workload`     | Name of the workload that the resource supports. | `kinetic-saas` |
| Data classification      | `ts-data-class`   | Sensitivity of data that the resource hosts. | `non-business` |
| Business criticality     | `ts-criticality`  | Business impact of the resource or supported workload. | `low` |
| Business unit            | `ts-business-unit`| Top-level division of your company that owns the subscription or workload that the resource belongs to. In smaller organizations, this tag might represent a single corporate or shared top-level organizational element. | `finance` |

### 4. 📊 Optional Tags
| **Tag Name**              | **Tag Key**        | **Description**  | **Example Value** |
|--------------------------|-------------------|------------------|------------------|
| Start date of the project | `ts-start-date`   | Date when the resource was first deployed. | `10-15-2020` |
| End date of the project   | `ts-end-date`     | Date when the resource is scheduled for retirement. | `10-15-2023` |
| Requester                 | `ts-requester`    | Team or individual who requested the creation of the resource. | `kinetic-dev` |


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
