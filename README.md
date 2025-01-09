# SonarScanner Analysis Action

This action runs SonarScanner CLI analysis on your codebase and uploads the results as artifacts.

## Sonar qube docs

- [Server](https://docs.sonarsource.com/sonarqube-server/latest/setup-and-upgrade/pre-installation/linux/)
- [CLI](https://docs.sonarsource.com/sonarqube-server/latest/analyzing-source-code/scanners/sonarscanner/)

## Features

- 🔍 Runs SonarScanner analysis without requiring a SonarQube server
- 📦 Packages and uploads analysis results as artifacts
- 💾 Caches SonarScanner installation for faster execution
- ⚙️ Configurable source paths and exclusions
- 📊 Generates a summary report

## Usage

```yaml
- uses: diekotto/sonar-scanner-analysis@v1
  with:
    project-key: my-project
    sources: src/
    exclusions: "**/test/**,**/node_modules/**"
```

## Inputs

| Input          | Description                       | Required | Default                         |
| -------------- | --------------------------------- | -------- | ------------------------------- |
| `project-key`  | Project key for the analysis      | Yes      | -                               |
| `sources`      | Source directories to analyze     | No       | `.`                             |
| `exclusions`   | Patterns to exclude from analysis | No       | `**/node_modules/**,**/dist/**` |
| `java-version` | Java version for SonarScanner     | No       | `17`                            |

## Outputs

The action uploads a ZIP file containing:

- Full analysis results
- Summary report
- Task report details
- Scanner logs

The artifacts are retained for 90 days and can be downloaded from the Actions tab.

## Example Workflow

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
      - uses: diekotto/sonar-scanner-analysis@v1
        with:
          project-key: my-project
```

## License

The scripts and documentation in this project are released under the MIT [License](LICENSE).
