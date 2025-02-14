# AWS Tagging Standards

## Overview
AWS supports resource tagging to help with organization, cost tracking, and access management. AWS tagging standards should be applied consistently across all resources to enable better governance and operational efficiency.

## Tagging Limitations in AWS
- **Maximum Tags per Resource**: Each AWS resource can have up to **50 tags**.
- **Tag Name and Value Length**:
  - Tag keys can be up to **128 characters**.
  - Tag values can be up to **256 characters**.
- **Case Sensitivity**: Tag keys are **case-sensitive**, meaning `Environment` and `environment` are treated as different tags.
- **Allowed Characters**: Tag keys and values may only contain alphanumeric characters, `-` , `_` , `.` (AWS allows other characters, but those violate our standards for other technologies)
- **Tag Propagation**: AWS does not automatically propagate tags across linked resources, such as EC2 instances and attached volumes.

## Standardized Tagging Format
To ensure uniformity, all tags in AWS should follow a structured naming convention prefixed with `ts` (tagging-standard).

### 🚀 Required Tags (For Governance & Cost Allocation)
| **Tag Key**         | **Example Value**       | **Purpose** |
|---------------------|------------------------|------------|
| `ts-application`   | `webapp-x`              | Identifies the application the resource supports. |
| `ts-business-unit` | `ecommerce`             | Top-level division of your company that owns the subscription or workload that the resource belongs to. In smaller organizations, this tag might represent a single corporate or shared top-level organizational element. |
| `ts-cost-center`   | `cc-12345`              | Links to a financial cost center. |
| `ts-criticality`   | `medium`  | Business impact of the resource or supported workload. |
| `ts-data-classification`   | `confidential`  | Sensitivity of data that the resource hosts. |
| `ts-dr`            | `mission-critical`      | Business criticality of the application, workload, or service. |
| `ts-environment`   | `production`            | Deployment environment of the application, workload, or service. |
| `ts-ops-team`   | `cloud-ops`  | Team accountable for day-to-day operations. |
| `ts-owner`         | `devops-team`           | Owner of the application, workload, or service. |
| `ts-project`       | `customer-portal`       | Tracks which project the resource belongs to. |
| `ts-region`      | `us-east-1`        | Helps in regional cost tracking. |
| `ts-service-class`   | `gold`                | Service-level agreement level of the application, workload, or service. |

### 🔍 Operational & Security Tags
| **Tag Key**          | **Example Value**         | **Purpose** |
|----------------------|--------------------------|------------|
| `ts-auto-shutdown`   | `enabled`                | Can be used by automation scripts to turn off resources. |
| `ts-compliance`      | `soc2`                   | Marks compliance requirements (soc2, hipaa, etc.). |
| `ts-ops-commitment`   | `enhanced-baseline`     | Level of operations support provided for the workload or resource.|
| `ts-start-date`   | `10-15-2020`                | Date when the application, workload, or service was first deployed. |
| `ts-end-date`   | `10-15-2024`                | Date when the application, workload, or service is scheduled for retirement. |

### 🔧 Automation & DevOps Tags
| **Tag Key**         | **Example Value**       | **Purpose** |
|---------------------|------------------------|------------|
| `ts-backup`        | `daily`                 | Used for automated backup policies. |
| `ts-maintenance-window` | `sun-2am`           | Defines when updates should be applied. |
| `ts-terraform`     | `managed`               | Indicates infrastructure-as-code ownership. |

### 📊 AWS-Specific Cost & Usage Report Tags
If you're using AWS **Cost Allocation Tags**, AWS requires activation in the **Billing Dashboard**.

| **Tag Key**       | **Example Value**  | **Purpose** |
|-------------------|-------------------|------------|
| `ts-approver` | `chris-contoso.com`     | Person responsible for approving costs related to the resource. |
| `ts-aws-account` | `123456789012`     | Associates resources with an AWS account. |
| `ts-budget-amount` | `200000`     | Money approved for the application, service, or workload. |
| `ts-requester` | `john-contoso.com`     | User who requested the creation of the application. |
| `ts-service`     | `ec2`              | Identifies the AWS service in use. |

## Tagging Best Practices
1. **Apply Tags Consistently**: Ensure all resources follow the standardized format.
2. **Use AWS Organizations and Service Control Policies (SCPs)**: Enforce tagging requirements across accounts.
3. **Automate Tagging with AWS Lambda and Tag Policies**: Ensure compliance using automation.
4. **Review and Update Tags Regularly**: Conduct periodic audits to maintain tag accuracy.
5. **Leverage AWS Cost Allocation Tags**: Assign relevant tags to track and optimize cloud spending.

By following these standards, teams can improve resource management, streamline operations, and enhance cost visibility in AWS.