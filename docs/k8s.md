# Kubernetes Tagging Standards

## Overview
Tagging in Kubernetes is primarily achieved through **labels** and **annotations**. Labels are used for identifying and organizing resources, while annotations store additional metadata.

## Tagging Limitations in Kubernetes
- **Tag Format:** Tags are applied as labels in key:value pairs
- **Character Limits**:
  - Tag keys: Up to 63 characters**.
  - Tag values: Up to 63 characters**.
- **Allowed characters:** Tag keys and values may only contain alphanumeric characters, `-` , `_` , `.` (Kubernetes allows other characters, but those violate our standards for other technologies)
- **Case Sensitivity**: Tags are **case-sensitive** (`env:Prod` is different from `env:prod`). All tags will be created in lowercase to comply with standards in other technologies.
- **Maximum Tags Per Resource**: There are no limits on the number of labels per resource

## Standardized Tagging Format
To ensure consistency, all Kubernetes labels should follow a structured naming convention prefixed with `ts` (tagging-standard).

### 🚀 Required K8s Tags
| Tag Name     | Tag Key          | Description                                                                                                     | Values                                            | Scope        |
|--------------|------------------|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------|-------------|
| Environment  | ts-env              | Deployment environment of the resource.                                                                         | prod<br>dev<br>qa<br>stage<br>sandbox<br>TBD      | General      |
| Cost center  | ts-cost-center   | Accounting cost center associated with the resource.                                                            | TBD                                               | General      |
| Team Owner   | ts-team-owner    | Team that owns and is responsible for the resource.                                                             | TBD                                               | General      |
| Customer ID  | ts-customer-id   | Customer IDs taken from SoA; '1' when not attributable to a specific customer.                                  | TBD                                               | General      |
| Product      | ts-product       | Epicor product(s) name associated with this resource; 'epicor-all' when not attributable to a specific product. | TBD                                               | General      |
| Compliance   | ts-compliance    | Specifies the compliance standards or regulations applicable to the service.                                    | pci-dss<br>sox<br>fedramp<br>gdpr<br>hipaa<br>soc | General      |

### ♾️ Suggested K8s DevOps Tags
| Tag Name           | Tag Key         | Description                                                                           | Values | Scope        |
|--------------------|-----------------|---------------------------------------------------------------------------------------|--------|--------------|
| Disaster recovery  | ts-dr           | Indicates this resource is part of a DR strategy; the value specifies its role in DR. | TBD    | General      |
| Provider           | ts-provider     | The cloud or data center provider.                                                    | TBD    | General      |
| Region             | ts-region       | Geographical region where the resource is created.                                    | TBD    | General      |
| Data Center        | ts-dc           | Specific data center or zone where the resource is created.                           | TBD    | General      |
| Operations team    | ts-ops-team     | Team accountable for day-to-day operations.                                           | TBD    | General      |
| Version            | ts-version      | Specifies the version of the application or service being deployed.                   | TBD    | General      |
| Application        | ts-application  | Added granularity if the workload is subdivided across multiple resources.            | TBD    | General      |

### 💰 Suggested K8s Business Tags
| Tag Name                 | Tag Key           | Description                                                                                             | Values | Scope   |
|--------------------------|-------------------|---------------------------------------------------------------------------------------------------------|--------|---------|
| Budget required/approved | ts-budget         | Money approved for the resource.                                                                        | TBD    | General |
| Approver name            | ts-approver       | Person responsible for approving costs related to the resource.                                         | TBD    | General |
| Service class            | ts-service-class  | Service-level agreement level of the resource.                                                          | TBD    | General |
| Workload                 | ts-workload       | Name of the workload that the resource supports.                                                        | TBD    | General |
| Data classification      | ts-data-class     | Sensitivity of data that the resource hosts.                                                            | TBD    | General |
| Business criticality     | ts-criticality    | Business impact of the resource or supported workload.                                                  | TBD    | General |
| Business unit            | ts-business-unit  | Top-level division of your company that owns the subscription or workload that the resource belongs to. | TBD    | General |

### 📊 Optional K8s Tags
| Tag Name                  | Tag Key         | Description                                                     | Values | Scope   |
|---------------------------|-----------------|-----------------------------------------------------------------|--------|---------|
| Start date of the project | ts-start-date   | Date when the resource was first deployed.                      | TBD    | General |
| End date of the project   | ts-end-date     | Date when the resource is scheduled for retirement.             | TBD    | General |
| Requester                 | ts-requester    | Team or individual who requested the creation of the resource.  | TBD    | General |

## Applying Multiple Values for K8s Tags
WIP

## Tagging Best Practices
1. **Use Labels for Selection and Grouping**: Leverage labels to group resources for scheduling and management.
2. **Limit Label Length**: Keep labels concise and meaningful.
3. **Use Annotations for Metadata**: Store descriptions, links, and non-identifying information in annotations.
4. **Automate Labeling**: Use admission controllers and GitOps practices to enforce labeling policies.
5. **Regularly Audit Labels**: Ensure tags remain accurate and relevant over time.

By following these standards, teams can enhance Kubernetes resource organization, improve automation, and streamline cost tracking.

