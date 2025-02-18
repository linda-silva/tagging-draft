# Azure Tagging Standards

## Overview
Azure supports resource tagging to help with organization, cost management, and governance. However, Azure has specific limitations and best practices that must be followed when implementing tagging standards.

## Tagging Limitations in Azure
- **Tag Format**: Tags are name-value pairs where names and values are specified separately. Names are required, values are optional.
- **Character Limits**:
  - Tag names: Up to **512 characters** (except for storage accounts, which have a limit of 128 characters).
  - Tag values: Up to **256 characters**.
- **Allowed Characters**: Tag names and values may only contain alphanumeric characters, `-` , `_` , `.` (Azure allows other characters, but those violate our standards for other technologies)
- **Case Sensitivity**: Tag names are **case-insensitive**, but values are **case-sensitive**.
- **Maximum Tags per Resource**: Each resource can have up to **50 tags**.
- **Inherited Tags**: Tags applied to resource groups are **not automatically inherited** by resources within the group.

## Standardized Tagging Format
To ensure consistency, all tags in Azure should follow a structured naming convention prefixed with `ts` (tagging-standard).

### 🚀 Required Azure Tags
| Tag Name     | Tag Key          | Description                                                                                                     | Values                                            | Scope        |
|--------------|------------------|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------|-------------|
| Environment  | ts-env              | Deployment environment of the resource.                                                                         | prod<br>dev<br>qa<br>stage<br>sandbox<br>TBD      | General      |
| Cost center  | ts-cost-center   | Accounting cost center associated with the resource.                                                            | TBD                                               | General      |
| Team Owner   | ts-team-owner    | Team that owns and is responsible for the resource.                                                             | TBD                                               | General      |
| Customer ID  | ts-customer-id   | Customer IDs taken from SoA; '1' when not attributable to a specific customer.                                  | TBD                                               | General      |
| Product      | ts-product       | Epicor product(s) name associated with this resource; 'epicor-all' when not attributable to a specific product. | TBD                                               | General      |
| Compliance   | ts-compliance    | Specifies the compliance standards or regulations applicable to the service.                                    | pci-dss<br>sox<br>fedramp<br>gdpr<br>hipaa<br>soc | General      |

### ♾️ Suggested Azure DevOps Tags
| Tag Name           | Tag Key         | Description                                                                           | Values | Scope        |
|--------------------|-----------------|---------------------------------------------------------------------------------------|--------|--------------|
| Disaster recovery  | ts-dr           | Indicates this resource is part of a DR strategy; the value specifies its role in DR. | TBD    | General      |
| Provider           | ts-provider     | The cloud or data center provider.                                                    | TBD    | General      |
| Region             | ts-region       | Geographical region where the resource is created.                                    | TBD    | General      |
| Data Center        | ts-dc           | Specific data center or zone where the resource is created.                           | TBD    | General      |
| Operations team    | ts-ops-team     | Team accountable for day-to-day operations.                                           | TBD    | General      |
| Version            | ts-version      | Specifies the version of the application or service being deployed.                   | TBD    | General      |
| Application        | ts-application  | Added granularity if the workload is subdivided across multiple resources.            | TBD    | General      |

### 💰 Suggested Azure Business Tags
| Tag Name                 | Tag Key           | Description                                                                                             | Values | Scope   |
|--------------------------|-------------------|---------------------------------------------------------------------------------------------------------|--------|---------|
| Budget required/approved | ts-budget         | Money approved for the resource.                                                                        | TBD    | General |
| Approver name            | ts-approver       | Person responsible for approving costs related to the resource.                                         | TBD    | General |
| Service class            | ts-service-class  | Service-level agreement level of the resource.                                                          | TBD    | General |
| Workload                 | ts-workload       | Name of the workload that the resource supports.                                                        | TBD    | General |
| Data classification      | ts-data-class     | Sensitivity of data that the resource hosts.                                                            | TBD    | General |
| Business criticality     | ts-criticality    | Business impact of the resource or supported workload.                                                  | TBD    | General |
| Business unit            | ts-business-unit  | Top-level division of your company that owns the subscription or workload that the resource belongs to. | TBD    | General |

### 📊 Optional Azure Tags
| Tag Name                  | Tag Key         | Description                                                     | Values | Scope   |
|---------------------------|-----------------|-----------------------------------------------------------------|--------|---------|
| Start date of the project | ts-start-date   | Date when the resource was first deployed.                      | TBD    | General |
| End date of the project   | ts-end-date     | Date when the resource is scheduled for retirement.             | TBD    | General |
| Requester                 | ts-requester    | Team or individual who requested the creation of the resource.  | TBD    | General |

## Applying Multiple Values for Azure Tags
WIP

## Tagging Best Practices
1. **Apply Tags Consistently**: Ensure that all resources follow the standardized format.
2. **Use Automation**: Utilize Azure Policy to enforce required tags on resource creation.
3. **Review and Update Tags Regularly**: Maintain accurate tags by conducting periodic audits.
4. **Use Resource Groups for Better Organization**: Group related resources and apply shared tags where applicable.
5. **Leverage Tagging for Cost Management**: Assign relevant tags to track and optimize cloud spending.

By following these standards, teams can ensure better resource management and alignment with organizational policies in Azure.

