# Azure Tagging Standards

## Overview
Azure supports resource tagging to help with organization, cost management, and governance. However, Azure has specific limitations and best practices that must be followed when implementing tagging standards.

## Tagging Limitations in Azure
- **Maximum Tags per Resource**: Each resource can have up to **50 tags**.
- **Tag Name and Value Length**:
  - Tag names can be up to **512 characters** (except for storage accounts, which have a limit of 128 characters).
  - Tag values can be up to **256 characters**.
- **Case Sensitivity**: Tag names are **case-insensitive**, but values are **case-sensitive**.
- **Restricted Characters**: Tag names and values **cannot** contain special characters like `<`, `>`, `%`, `&`, `?`.
- **Inherited Tags**: Tags applied to resource groups are **not automatically inherited** by resources within the group.

## Standardized Tagging Format
To ensure consistency, all tags in Azure should follow a structured naming convention prefixed with `TS1` (Tagging Standard 1).

### Required Tags
| Tag Key            | Example Value        | Description                                      |
|--------------------|---------------------|--------------------------------------------------|
| TS1-Environment   | Production          | Identifies the environment (Dev, Test, Prod).   |
| TS1-Owner         | DevOps Team         | Defines ownership of the resource.              |
| TS1-CostCenter    | 12345               | Maps resource costs to a financial unit.        |
| TS1-Application   | WebAppX             | Associates the resource with an application.    |
| TS1-Compliance    | HIPAA               | Indicates compliance requirements.              |

### Optional Tags
| Tag Key            | Example Value        | Description                                      |
|--------------------|---------------------|--------------------------------------------------|
| TS1-Project       | Alpha               | Associates resources with a project.            |
| TS1-CreationDate  | 2025-02-06          | Indicates when the resource was created.        |
| TS1-BusinessUnit | IT                   | Specifies the business unit responsible.        |

## Tagging Best Practices
1. **Apply Tags Consistently**: Ensure that all resources follow the standardized format.
2. **Use Automation**: Utilize Azure Policy to enforce required tags on resource creation.
3. **Review and Update Tags Regularly**: Maintain accurate tags by conducting periodic audits.
4. **Use Resource Groups for Better Organization**: Group related resources and apply shared tags where applicable.
5. **Leverage Tagging for Cost Management**: Assign relevant tags to track and optimize cloud spending.

By following these standards, teams can ensure better resource management and alignment with organizational policies in Azure.

