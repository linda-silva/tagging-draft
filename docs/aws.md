# AWS Tagging Standards

## Overview
AWS supports resource tagging to help with organization, cost tracking, and access management. AWS tagging standards should be applied consistently across all resources to enable better governance and operational efficiency.

## Tagging Limitations in AWS
- **Maximum Tags per Resource**: Each AWS resource can have up to **50 tags**.
- **Tag Name and Value Length**:
  - Tag keys can be up to **128 characters**.
  - Tag values can be up to **256 characters**.
- **Case Sensitivity**: Tag keys are **case-sensitive**, meaning `Environment` and `environment` are treated as different tags.
- **Restricted Characters**: Tag keys and values **cannot** contain the following characters: `^,*,<,>,%,&,$,@,!,#,(,),\,/`.
- **Tag Propagation**: AWS does not automatically propagate tags across linked resources, such as EC2 instances and attached volumes.

## Standardized Tagging Format
To ensure uniformity, all tags in AWS should follow a structured naming convention prefixed with `TS1` (Tagging Standard 1).

### Required Tags
| Tag Key           | Example Value      | Description                                      |
|-------------------|-------------------|--------------------------------------------------|
| TS1-Environment  | Production        | Identifies the environment (Dev, Test, Prod).   |
| TS1-Owner        | DevOps Team       | Defines ownership of the resource.              |
| TS1-CostCenter   | 12345             | Maps resource costs to a financial unit.        |
| TS1-Application  | WebAppX           | Associates the resource with an application.    |
| TS1-Compliance   | PCI-DSS           | Indicates compliance requirements.              |

### Optional Tags
| Tag Key          | Example Value      | Description                                      |
|------------------|-------------------|--------------------------------------------------|
| TS1-Project     | Alpha             | Associates resources with a project.            |
| TS1-CreationDate| 2025-02-06        | Indicates when the resource was created.        |
| TS1-BusinessUnit| IT                 | Specifies the business unit responsible.        |

## Tagging Best Practices
1. **Apply Tags Consistently**: Ensure all resources follow the standardized format.
2. **Use AWS Organizations and Service Control Policies (SCPs)**: Enforce tagging requirements across accounts.
3. **Automate Tagging with AWS Lambda and Tag Policies**: Ensure compliance using automation.
4. **Review and Update Tags Regularly**: Conduct periodic audits to maintain tag accuracy.
5. **Leverage AWS Cost Allocation Tags**: Assign relevant tags to track and optimize cloud spending.

By following these standards, teams can improve resource management, streamline operations, and enhance cost visibility in AWS.

