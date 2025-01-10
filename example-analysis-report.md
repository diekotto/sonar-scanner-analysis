# 🔍 SonarQube Analysis Results
## Project Information
- **Project Key**: example-project
- **Date**: Fri Jan 10 07:51:42 UTC 2025
- **Runner**: Linux
## 🎯 Quality Gate Status
**Status**: OK
## 📊 Metrics
| Metric | Value | Rating |
|--------|--------|--------|
| Bugs | 0 | A |
| Vulnerabilities | 0 | A |
| Code_smells | 5 | A |
| Coverage | 0.0% | - |
| Duplicated_lines_density | 0.0% | - |
## 🔍 Issues Breakdown
### By Type
| Type | Count |
|------|-------|
| CODE_SMELL | 5 |
### By Severity
| Severity | Count |
|----------|--------|
| CRITICAL | 2 |
| MAJOR | 1 |
| MINOR | 2 |

## 🔍 Detailed Issues
### 📝 Issue Details
| Type | Severity | File | Line | Message |
|------|-----------|------|------|---------|
| CODE_SMELL | CRITICAL | src/index.js | 9 | Refactor this function to reduce its Cognitive Complexity from 28 to the 15 allowed. |
| CODE_SMELL | CRITICAL | src/index.js | 108 | Refactor this redundant 'await' on a non-promise. |
| CODE_SMELL | MINOR | src/index.js | 116 | Remove this redundant jump. |
| CODE_SMELL | MINOR | src/utils/fileFilter.js | 41 | Replace this if-then-else flow by a single return statement. |
| CODE_SMELL | MAJOR | src/utils/fileFilter.js | 64 | Remove this commented out code. |

### ⚠️ Most Common Rules Violated
| Rule | Description | Occurrences |
|------|-------------|-------------|
| javascript:S4123 | "await" should only be used with promises | 1 |
| javascript:S3776 | Cognitive Complexity of functions should not be too high | 1 |
| javascript:S3626 | Jump statements should not be redundant | 1 |
| javascript:S125 | Sections of code should not be commented out | 1 |
| javascript:S1126 | Return of boolean expressions should not be wrapped into an "if-then-else" statement | 1 |
