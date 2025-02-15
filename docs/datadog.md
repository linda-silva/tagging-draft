# DataDog Tagging Standards

## Overview
Tagging in DataDog is essential for organizing, filtering, and aggregating metrics, logs, and traces. Consistent tagging helps improve monitoring, troubleshooting, and cost analysis.

## Tagging Limitations in DataDog
- **Tag Format**: Tags are key-value pairs formatted as `key:value`.
- **Character Limits**:
  - Tag keys: Up to **200 characters**.
  - Tag values: Up to **200 characters**.
- **Allowed Characters**: Tags can contain alphanumeric characters, underscores (`_`), hyphens (`-`), colons (`:`), and periods (`.`).
- **Case Sensitivity**: Tags are **case-sensitive** (`env:Prod` is different from `env:prod`).
- **Number of Tags**: Each resource can have up to **1000 tags**.

## Standardized Tagging Format
To ensure consistency, all DataDog tags should follow a structured naming convention prefixed with `ts-` (tagging-standard).

The exceptions to this standard are the `env` and `service` tags. These specific keys are required by DataDog, so the `ts-` prefix not required

### **Required Tags**
| Tag Key            | Example Value   | Description                                      |
|--------------------|----------------|--------------------------------------------------|
| TS1-environment   | production      | Identifies the environment (dev, test, prod).   |
| TS1-service       | web-api         | Associates data with a specific service.        |
| TS1-owner        | devops-team     | Defines responsibility for the resource.        |
| TS1-region       | us-east-1       | Specifies the cloud region.                     |
| TS1-compliance   | GDPR            | Indicates compliance requirements.              |

### **Optional Tags**
| Tag Key           | Example Value   | Description                                      |
|-------------------|----------------|--------------------------------------------------|
| TS1-application  | webapp-x        | Associates the resource with an application.    |
| TS1-team         | backend-team    | Defines the responsible team.                   |
| TS1-cost-center  | 12345           | Maps the resource to a financial unit.         |

## Tagging Best Practices
1. **Apply Tags Consistently**: Use a uniform structure for all resources.
2. **Use Automation**: Implement tagging policies using DataDog APIs and automation scripts.
3. **Limit the Number of Tags**: Avoid excessive tags to prevent complexity.
4. **Use Tags for Efficient Filtering**: Leverage tags to segment and analyze metrics and logs effectively.
5. **Review and Update Tags Regularly**: Conduct audits to ensure proper usage and relevancy.

By following these tagging standards, teams can enhance observability, improve operational efficiency, and gain better insights in DataDog.

