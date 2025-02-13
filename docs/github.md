# GitHub Enterprise Tagging Standards

## Overview
Tagging in GitHub Enterprise is used to categorize and manage teams within the organization. While GitHub does not have a native tagging system for repositories, we can apply structured tags at the Team level using the description field.

This doc does not cover tagging for versions, pull requests, issues or repositories as those are outside the scope of this discussion.

## Tagging Limitations in GitHub
- **Team Descriptions**:
  - Maxium length of **255 characters**
  - Support plain text only (no structured metadata like JSON or Markdown)
  - No built-in search functionality for descriptions in the GitHub UI (requires API queries)

## Standardized Tagging Format
To ensure uniformity, GitHub Enterprise tagging should follow a structured naming convention prefixed with `TS1` (Tagging Standard 1).

### Team-Level Tagging

Teams can include structured tags within their description field using a comma-separated format:

Example:
```text
TS1-DevOps, TS1-Microservices, TS1-Internal-Tool
```

### **Required Tags**
| Tag Key          | Example Value       | Description                                   |
|------------------|--------------------|-----------------------------------------------|
| TS1-product     | ABCPlatform         | Associates the team with a specific product. |
| TS1-service     | DevOps              | Specifies the team's function or service.    |
| TS1-region      | US-East-1           | Indicates the region of operations.          |
| TS1-compliance  | SOC2                | Identifies compliance frameworks followed.   |
| TS1-owner       | Engineering         | Specifies the department responsible.        |

## Tagging Best Practices
1. **Apply Consistently**: Ensure all team descriptions follow the naming conventions.
2. **Keep Descriptions Concise**: Stay within the 255-character limit while maintaining clarity.
3. **Automate with the GitHub API**: Use scripts to extract, audit, and enforce tagging.
4. **Review Periodically**: Conduct regular audits to ensure tags remain relevant.
5. **Avoid Over-Tagging**: Use only essential tags to prevent complexity.

By following these standards, teams can improve visibility, streamline organizational structures, and enhance tracking within GitHub Enterprise.


