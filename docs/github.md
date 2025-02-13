# GitHub Enterprise Tagging Standards

## Overview
Tagging in GitHub Enterprise is used to categorize and manage repositories, issues, pull requests, and workflows. While GitHub does not have a native tagging system for repositories, organizations can use labels, topics, and metadata to apply consistent tags across projects.

This doc focuses on resource tagging at the repository and organization level.
This doc does not cover version, Pull Request or issue-level tagging as those are outside the scope of this discussion.

## Tagging Limitations in GitHub
- **Repository Topics**:
  - Each repository can have up to **20 topics** for categorization.
  - Each topic can have up to **50 characters**
  - Characters are limited to lowercase alphanumeric and -
- **Team Descriptions**:
  - Team descriptions can include structured tags
  - Maxium length of **255 characters**

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

## Tagging Best Practices
1. **Apply Consistently**: Ensure all repositories, issues, and workflows follow the naming conventions.
2. **Automate with GitHub Actions**: Use automated workflows to enforce tagging rules.
3. **Limit the Number of Tags**: Use only meaningful tags to prevent clutter.
4. **Review Periodically**: Regularly audit and update tags to align with project changes.
5. **Leverage GitHub Topics for Discoverability**: Ensure repositories use relevant topics for better organization.

By following these standards, teams can improve visibility, streamline workflows, and enhance repository organization within GitHub Enterprise.

