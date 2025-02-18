# AWS Tagging Standards

## Overview
AWS supports resource tagging to help with organization, cost tracking, and access management. AWS tagging standards should be applied consistently across all resources to enable better governance and operational efficiency.

## **AWS Tagging Constraints**
- **Tag Format**: Tags are key-value pairs where keys and values are specified separately. Keys are required, values are optional.
- **Character Limits**:
  - Tag keys: Up to **128 characters**.
  - Tag values: Up to **256 characters**.
- **Allowed Characters**: Tag keys and values may only contain alphanumeric characters, `-` , `_` , `.` (AWS allows other characters, but those violate our standards for other technologies)
- **Case Sensitivity**: Tag keys are **case-sensitive**, meaning `Environment` and `environment` are treated as different tags. All tags will be created in lowercase to comply with standards in other technologies.
- **Maximum Tags per Resource**: Each AWS resource can have up to **50 tags**.
- **Tag Propagation**: AWS does not automatically propagate tags across linked resources, such as EC2 instances and attached volumes. AWS generated tags are typically prefixed with `aws`, so this prefix cannot be used in user-defined tag keys.

## Naming Standards
To ensure uniformity, all tags in AWS should follow a structured naming convention prefixed with `ts` (tagging-standard).

### 🚀 Required AWS Tags
| Tag Name     | Tag Key          | Description                                                                                                     | Values                                            | Scope        |
|--------------|------------------|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------|-------------|
| Environment  | ts-env              | Deployment environment of the resource.                                                                         | prod<br>dev<br>qa<br>stage<br>sandbox<br>TBD      | General      |
| Cost center  | ts-cost-center   | Accounting cost center associated with the resource.                                                            | TBD                                               | General      |
| Team Owner   | ts-team-owner    | Team that owns and is responsible for the resource.                                                             | TBD                                               | General      |
| Customer ID  | ts-customer-id   | Customer IDs taken from SoA; '1' when not attributable to a specific customer.                                  | TBD                                               | General      |
| Product      | ts-product       | Epicor product(s) name associated with this resource; 'epicor-all' when not attributable to a specific product. | TBD                                               | General      |
| Compliance   | ts-compliance    | Specifies the compliance standards or regulations applicable to the service.                                    | pci-dss<br>sox<br>fedramp<br>gdpr<br>hipaa<br>soc | General      |

### ♾️ Suggested AWS DevOps Tags
| Tag Name           | Tag Key         | Description                                                                           | Values | Scope        |
|--------------------|-----------------|---------------------------------------------------------------------------------------|--------|--------------|
| Disaster recovery  | ts-dr           | Indicates this resource is part of a DR strategy; the value specifies its role in DR. | TBD    | General      |
| Provider           | ts-provider     | The cloud or data center provider.                                                    | TBD    | General      |
| Region             | ts-region       | Geographical region where the resource is created.                                    | TBD    | General      |
| Data Center        | ts-dc           | Specific data center or zone where the resource is created.                           | TBD    | General      |
| Operations team    | ts-ops-team     | Team accountable for day-to-day operations.                                           | TBD    | General      |
| Version            | ts-version      | Specifies the version of the application or service being deployed.                   | TBD    | General      |
| Application        | ts-application  | Added granularity if the workload is subdivided across multiple resources.            | TBD    | General      |

### 💰 Suggested AWS Business Tags
| Tag Name                 | Tag Key           | Description                                                                                             | Values | Scope   |
|--------------------------|-------------------|---------------------------------------------------------------------------------------------------------|--------|---------|
| Budget required/approved | ts-budget         | Money approved for the resource.                                                                        | TBD    | General |
| Approver name            | ts-approver       | Person responsible for approving costs related to the resource.                                         | TBD    | General |
| Service class            | ts-service-class  | Service-level agreement level of the resource.                                                          | TBD    | General |
| Workload                 | ts-workload       | Name of the workload that the resource supports.                                                        | TBD    | General |
| Data classification      | ts-data-class     | Sensitivity of data that the resource hosts.                                                            | TBD    | General |
| Business criticality     | ts-criticality    | Business impact of the resource or supported workload.                                                  | TBD    | General |
| Business unit            | ts-business-unit  | Top-level division of your company that owns the subscription or workload that the resource belongs to. | TBD    | General |

### 📊 Optional AWS Tags
| Tag Name                  | Tag Key         | Description                                                     | Values | Scope   |
|---------------------------|-----------------|-----------------------------------------------------------------|--------|---------|
| Start date of the project | ts-start-date   | Date when the resource was first deployed.                      | TBD    | General |
| End date of the project   | ts-end-date     | Date when the resource is scheduled for retirement.             | TBD    | General |
| Requester                 | ts-requester    | Team or individual who requested the creation of the resource.  | TBD    | General |

## Applying Multiple Values for AWS Tags
WIP

## Tagging Best Practices
1. **Apply Tags Consistently**: Ensure all resources follow the standardized format.
2. **Use AWS Organizations and Service Control Policies (SCPs)**: Enforce tagging requirements across accounts.
3. **Automate Tagging with AWS Lambda and Tag Policies**: Ensure compliance using automation.
4. **Review and Update Tags Regularly**: Conduct periodic audits to maintain tag accuracy.
5. **Leverage AWS Cost Allocation Tags**: Assign relevant tags to track and optimize cloud spending.

By following these standards, teams can improve resource management, streamline operations, and enhance cost visibility in AWS.