# DataDog Tagging Standards

## Overview
Tagging in DataDog is essential for organizing, filtering, and aggregating metrics, logs, and traces. Consistent tagging helps improve monitoring, troubleshooting, and cost analysis.

## **DataDog Tagging Constraints**
- **Tag Format**: Tags are key-value pairs formatted as `key:value`.
- **Character Limits**:
  - Tag keys: Up to **200 characters**.
  - Tag values: Up to **200 characters**.
- **Allowed Characters**: Tag keys and values may only contain alphanumeric characters, `-` , `_` , `.` (DataDog allows other characters, but those violate our standards for other technologies)
- **Case Sensitivity**: Tags are **case-sensitive** (`env:Prod` is different from `env:prod`).
- **Maxium Tags Per Resource**: Each resource can have up to **1000 tags**.

## Standardized Tagging Format
To ensure consistency, all DataDog tags should follow a structured naming convention prefixed with `ts-` (tagging-standard).

The exceptions to this standard are the `env` and `service` tags. These specific keys are required by DataDog, so the `ts-` prefix not required

### 🚀 Required DataDog Tags
| Tag Name     | Tag Key          | Description                                                                                                     | Values                                            | Scope        |
|--------------|------------------|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------|-------------|
| Environment  | env              | Deployment environment of the resource.                                                                         | prod<br>dev<br>qa<br>stage<br>sandbox<br>TBD      | General      |
| Service      | service          | Defines the specific service or function being monitored.                                                       | TBD                                               | DataDog only |
| Cost center  | ts-cost-center   | Accounting cost center associated with the resource.                                                            | TBD                                               | General      |
| Team Owner   | ts-team-owner    | Team that owns and is responsible for the resource.                                                             | TBD                                               | General      |
| Customer ID  | ts-customer-id   | Customer IDs taken from SoA; '1' when not attributable to a specific customer.                                  | TBD                                               | General      |
| Product      | ts-product       | Epicor product(s) name associated with this resource; 'epicor-all' when not attributable to a specific product. | TBD                                               | General      |

| Network      | ts-network       | Describes the network segment where the service is running.                                                     | TBD                                               | DataDog only |
| Compliance   | ts-compliance    | Specifies the compliance standards or regulations applicable to the service.                                    | pci-dss<br>sox<br>fedramp<br>gdpr<br>hipaa<br>soc | General      |

### ♾️ Suggested DataDog DevOps Tags
| Tag Name           | Tag Key         | Description                                                                           | Values | Scope        |
|--------------------|-----------------|---------------------------------------------------------------------------------------|--------|--------------|
| Disaster recovery  | ts-dr           | Indicates this resource is part of a DR strategy; the value specifies its role in DR. | TBD    | General      |
| Provider           | ts-provider     | The cloud or data center provider.                                                    | TBD    | General      |
| Region             | ts-region       | Geographical region where the resource is created.                                    | TBD    | General      |
| Data Center        | ts-dc           | Specific data center or zone where the resource is created.                           | TBD    | General      |
| Operations team    | ts-ops-team     | Team accountable for day-to-day operations.                                           | TBD    | General      |
| Version            | ts-version      | Specifies the version of the application or service being deployed.                   | TBD    | General      |
| Application        | ts-application  | Added granularity if the workload is subdivided across multiple resources.            | TBD    | General      |
| Runtime            | ts-runtime      | Names the application or software being used.                                         | TBD    | DataDog only |
| Role               | ts-role         | Describes the role of the service or component within the architecture.               | TBD    | DataDog only |
| Platform           | ts-platform     | Specifies the underlying platform or ecosystem on which the service operates.         | TBD    | DataDog only |
| Journey            | ts-journey      | Tracks key user journeys across various processes.                                    | TBD    | DataDog only |

### 💰 Suggested DataDog Business Tags
| Tag Name                 | Tag Key           | Description                                                                                             | Values | Scope   |
|--------------------------|-------------------|---------------------------------------------------------------------------------------------------------|--------|---------|
| Budget required/approved | ts-budget         | Money approved for the resource.                                                                        | TBD    | General |
| Approver name            | ts-approver       | Person responsible for approving costs related to the resource.                                         | TBD    | General |
| Service class            | ts-service-class  | Service-level agreement level of the resource.                                                          | TBD    | General |
| Workload                 | ts-workload       | Name of the workload that the resource supports.                                                        | TBD    | General |
| Data classification      | ts-data-class     | Sensitivity of data that the resource hosts.                                                            | TBD    | General |
| Business criticality     | ts-criticality    | Business impact of the resource or supported workload.                                                  | TBD    | General |
| Business unit            | ts-business-unit  | Top-level division of your company that owns the subscription or workload that the resource belongs to. | TBD    | General |

### 📊 Optional DataDog Tags
| Tag Name                  | Tag Key         | Description                                                     | Values | Scope   |
|---------------------------|-----------------|-----------------------------------------------------------------|--------|---------|
| Start date of the project | ts-start-date   | Date when the resource was first deployed.                      | TBD    | General |
| End date of the project   | ts-end-date     | Date when the resource is scheduled for retirement.             | TBD    | General |
| Requester                 | ts-requester    | Team or individual who requested the creation of the resource.  | TBD    | General |

## Applying Multiple Values for DataDog Tags
WIP

## Tagging Best Practices
1. **Apply Tags Consistently**: Use a uniform structure for all resources.
2. **Use Automation**: Implement tagging policies using DataDog APIs and automation scripts.
3. **Limit the Number of Tags**: Avoid excessive tags to prevent complexity.
4. **Use Tags for Efficient Filtering**: Leverage tags to segment and analyze metrics and logs effectively.
5. **Review and Update Tags Regularly**: Conduct audits to ensure proper usage and relevancy.

By following these tagging standards, teams can enhance observability, improve operational efficiency, and gain better insights in DataDog.

