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

### 🚀 Required Tags
| **Tag Key**         | **Example Value**       | **Purpose** |
|---------------------|------------------------|------------|
| `ts-cost-center`   | `55332`              | Accounting cost center associated with the resource. |
| `ts-env`   | `production`            | Deployment environment of the resource. |
| `ts-team-owner`         | `dev-ops`           | Team that owns and is responsible for the resource. |

### 💰 Suggested Business Related Tags
| **Tag Key**         | **Example Value**       | **Purpose** |
|---------------------|------------------------|------------|
| `ts-application`   | `issue-tracking-system` | Added granularity, if the workload is subdivided across multiple resources. |
| `ts-business-unit` | `finance`             | Top-level division of your company that owns the subscription or workload that the resource belongs to. In smaller organizations, this tag might represent a single corporate or shared top-level organizational element. |

| `ts-criticality`   | `medium`  | Business impact of the resource or supported workload. |
| `ts-data-class`   | `confidential`  | Sensitivity of data that the resource hosts. |
| `ts-dr`            | `primary`      | If this tag exists, it indicates this resource is a participant in a DR strategy. The value of the tag indicates what the function of this resource is in the DR scope. |

| `ts-ops-team`   | `cloud-operations`  | Team accountable for day-to-day operations. |

| `ts-project`       | `customer-portal`       | Tracks which project the resource belongs to. |
| `ts-region`      | `uk-south`        | Geographical region where the resource is created. |
| `ts-service-class`   | `gold`                | Service-level agreement level of the resource. |
| `ts-provider`   | `aws`                | The cloud or data center provider. |
| `ts-dc`   | `us-west-1a`              | Specific data center or zone where the resource is created. |
| `ts-workload`   | `kinetic-saas`              | Name of the workload that the resource supports. |

### 🔍 Operational & Security Tags
| **Tag Key**          | **Example Value**         | **Purpose** |
|----------------------|--------------------------|------------|
| `ts-auto-shutdown`   | `enabled`                | Can be used by automation scripts to turn off resources. |
| `ts-compliance`      | `soc2`                   | Marks compliance requirements (soc2, hipaa, etc.). |
| `ts-start-date`   | `10-15-2020`                | Date when the resource was first deployed. |
| `ts-end-date`   | `10-15-2024`                | Date when the resource is scheduled for retirement. |

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
| `ts-approver` | `chris-smith`     | Person responsible for approving costs related to the resource. |
| `ts-aws-account` | `123456789012`     | Associates resources with an AWS account. |
| `ts-budget` | `200000`     | Money approved for the resource. |
| `ts-requester` | `kinetic-dev`     | Team or individual who requested the creation of the resource. |
| `ts-service`     | `ec2`              | Identifies the AWS service in use. |

## Tagging Best Practices
1. **Apply Tags Consistently**: Ensure all resources follow the standardized format.
2. **Use AWS Organizations and Service Control Policies (SCPs)**: Enforce tagging requirements across accounts.
3. **Automate Tagging with AWS Lambda and Tag Policies**: Ensure compliance using automation.
4. **Review and Update Tags Regularly**: Conduct periodic audits to maintain tag accuracy.
5. **Leverage AWS Cost Allocation Tags**: Assign relevant tags to track and optimize cloud spending.

By following these standards, teams can improve resource management, streamline operations, and enhance cost visibility in AWS.