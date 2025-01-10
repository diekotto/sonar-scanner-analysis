# SonarScanner Analysis Action

A GitHub Action that runs SonarQube analysis using local Docker containers, providing a self-contained analysis environment without requiring an external SonarQube server.

## Features

- 🐳 Runs SonarQube server and scanner in Docker containers
- 🔒 Self-contained analysis environment
- 📊 Detailed analysis reports as workflow artifacts
- 🚀 Easy integration with existing workflows
- 📝 Comprehensive quality metrics and issue tracking
- ⚡ Supports custom source paths and exclusions

## Prerequisites

- GitHub Actions runner with Docker support (e.g., `ubuntu-latest`)
- Repository access to run workflows

## Usage

Create or update your workflow file (e.g., `.github/workflows/sonar-analysis.yml`):

```yaml
name: Code Analysis

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  analyze:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run SonarScanner Analysis
        uses: diekotto/sonar-scanner-analysis@v1
        with:
          project-key: your-project-key
          sources: src/
          exclusions: "**/*.test.js,**/node_modules/**"
```

## Inputs

| Input             | Description                                    | Required | Default                         |
| ----------------- | ---------------------------------------------- | -------- | ------------------------------- |
| `project-key`     | Project key for the analysis                   | Yes      | -                               |
| `sources`         | Source directories to analyze                  | No       | `.`                             |
| `exclusions`      | Patterns to exclude from analysis              | No       | ` ` |
| `wait-for-server` | Max time in seconds to wait for SonarQube server   | No       | `60`                            |
| `retention-days`  | Number of days to retain the analysis artifact | No       | `7`                             |

## Outputs

The action generates a detailed analysis report that includes:

- Project quality gate status
- Key metrics (bugs, vulnerabilities, code smells, etc.)
- Issue breakdown by type and severity
- Detailed issue list with file locations and descriptions
- Most commonly violated rules

The report is available as a workflow artifact and is also added to the workflow summary.

## Example Analysis Report

Here's a snippet of what the analysis report looks like:

```markdown
# 🔍 SonarQube Analysis Results

## Project Information

- **Project Key**: example-project
- **Date**: Fri Jan 10 07:51:42 UTC 2025
- **Runner**: Linux

## 🎯 Quality Gate Status

**Status**: OK

## 📊 Metrics

| Metric                   | Value | Rating |
| ------------------------ | ----- | ------ |
| Bugs                     | 0     | A      |
| Vulnerabilities          | 0     | A      |
| Code_smells              | 5     | A      |
| Coverage                 | 0.0%  | -      |
| Duplicated_lines_density | 0.0%  | -      |
```

## License

This action is released under the MIT License. See the [LICENSE](LICENSE) file for details.

### Third-Party Licenses

This action uses the following Docker images, both licensed under GNU LGPL v3:

- `sonarqube:lts-community`
- `sonarsource/sonar-scanner-cli`

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

If you encounter any problems or have suggestions, please open an issue in the repository.

---

⭐ If you find this action useful, please consider giving it a star!
