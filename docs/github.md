# GitHub Enterprise Tagging Standards

## Overview
Tagging in GitHub Enterprise is used to categorize and manage repositories, issues, pull requests, and workflows. While GitHub does not have a native tagging system for repositories, organizations can use labels, topics, and metadata to apply consistent tags across projects.

## Tagging Limitations in GitHub
- **Repository Topics**: Each repository can have up to **20 topics** for categorization.
- **Issue & Pull Request Labels**:
  - Labels can be up to **50 characters long**.
  - Colors are assigned in hexadecimal format.
  - Labels are case-insensitive.
- **Branch and Release Tags**:
  - Tags must follow Git’s naming rules (no spaces, avoid special characters like `~^:?*[]`).
- **Actions & Workflows Metadata**:
  - YAML workflows can include `tags` in metadata but must follow structured formats.

## Standardized Tagging Format
To ensure uniformity, GitHub Enterprise tagging should follow a structured naming convention prefixed with `TS1` (Tagging Standard 1).

### **Repository Topics**
Use standardized topics to classify repositories:
- `TS1-product-name`
- `TS1-service-type`
- `TS1-team-name`

Example:
```text
TS1-DevOps, TS1-Microservices, TS1-Internal-Tool
```

### **Issue & PR Labels**
| Label Key          | Example Value  | Description                                   |
|--------------------|---------------|-----------------------------------------------|
| TS1-Environment   | Production     | Identifies the environment (Dev, Test, Prod).|
| TS1-Priority      | High           | Categorizes the urgency of the task.         |
| TS1-Compliance    | SOC2           | Indicates compliance requirements.           |
| TS1-Application   | WebAppX        | Associates the issue/PR with an application. |
| TS1-Owner        | DevOps Team     | Defines responsibility.                      |

### **Branch and Release Tags**
| Tag Format          | Example                | Description                                |
|---------------------|------------------------|--------------------------------------------|
| `TS1-release-vX.Y` | `TS1-release-v1.2`     | Indicates versioned releases.             |
| `TS1-feature-xxx`  | `TS1-feature-api-refactor` | Identifies feature branches.            |
| `TS1-hotfix-xxx`   | `TS1-hotfix-login-bug` | Marks critical bug fixes.                 |

## Tagging Best Practices
1. **Apply Consistently**: Ensure all repositories, issues, and workflows follow the naming conventions.
2. **Automate with GitHub Actions**: Use automated workflows to enforce tagging rules.
3. **Limit the Number of Tags**: Use only meaningful tags to prevent clutter.
4. **Review Periodically**: Regularly audit and update tags to align with project changes.
5. **Leverage GitHub Topics for Discoverability**: Ensure repositories use relevant topics for better organization.

By following these standards, teams can improve visibility, streamline workflows, and enhance repository organization within GitHub Enterprise.

