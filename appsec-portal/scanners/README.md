---
description: >-
  The AppSec Portal uses a variety of importers to integrate with popular
  scanners
---

# 🔬 Scanners

* [**Importing reports from scanners to AppSec Portal**](importing-reports-from-scanners-to-appsec-portal/)

To configure the scanner, please refer to the [**scanner settings**](../general-portal-settings/scanner-settings/) section.

Here are the details of each **importer** supported by AppSec Portal

#### Code scanners:

* **`Bandit`**: imports scan results from [**Bandit Scanner** and **GitLab Bandit scanner**](scanner-description/code-scanners/bandit.md), which is a tool for finding security issues in _Python_ _code_. It checks Python code for common security issues such as hardcoded passwords, SQL injections, and more.
* **`Checkov`**: imports scan results from [**Checkov Scanner**](scanner-description/code-scanners/checkov.md), which is a tool for finding security issues in Infrastructure As Code. It provides static analysis of Terraform, CloudFormation, and Kubernetes code to identify misconfigurations and potential security issues.
* **`CodeQL`**: imports scan results from [**CodeQL Scanner**](scanner-description/code-scanners/codeql.md), which is a tool for analyzing source code to find security vulnerabilities such as SQL injection, cross-site scripting (XSS), buffer overflows, and more.
* **`ESLint`**: imports scan results from [**ESLint Scanner** and **GitLab ESLint**](scanner-description/code-scanners/eslint.md), which is a tool for finding security issues in JavaScript code. It checks JavaScript code for common security issues such as cross-site scripting (XSS), SQL injection, and more.
* **`Gemnasium` :** imports scan results from [**GitLab** **Gemnasium Scanner**](scanner-description/code-scanners/gemnasium.md), which is a tool that identifies vulnerabilities and security issues within project dependencies.
* **`Gosec`**: imports scan results from [**Gosec Scanner**](scanner-description/code-scanners/gosec.md), which is a tool for finding security issues in Go code. It helps identify potential security vulnerabilities in Go code.
* **`Hadolint`**: imports scan results from [**Hadolint Dockerfile Check Scanner**](scanner-description/code-scanners/hadolint.md), a Dockerfile linter that helps ensure Dockerfile syntax correctness, adherence to best practices, and identification of potential issues related to Docker image creation. It focuses on code quality and conformity to Dockerfile standards, aiding in the creation of secure and well-structured Docker images.
* **`KICS`**:  imports scan results from [**GitLab** **KICS Scanner**](scanner-description/code-scanners/kics.md) (Keeping Infrastructure as Code Secure), wich is designed to detect security vulnerabilities and policy violations in infrastructure-as-code (IaC) files.
* **`PHPCodeSniffer`**: mports scan results from [**PHP\_CodeSniffer**](scanner-description/code-scanners/php\_codesniffer.md), wich is tokenizes PHP files and detects violations of a defined set of coding standards.
* **`Retire.js`**: imports scan results from [**Retire.js Scanner**](scanner-description/code-scanners/retire.js.md), a tool designed to analyze JavaScript code for deprecated and vulnerable libraries and dependencies. It focuses on identifying outdated or known vulnerable components within JavaScript code, contributing to the enhancement of web application security.
* **`Semgrep`**: imports scan results from [**Semgrep scanner** and **GitLab Semgrep scanner**](scanner-description/code-scanners/semgrep.md), which is a tool for finding security issues in code. It provides static analysis of code in various languages and helps identify potential security vulnerabilities.
* **`Terrascan`**: imports scan results from [**Terrascan Scanner**](scanner-description/code-scanners/terrascan.md), which is a tool for finding security issues in Terraform code. It helps identify potential security vulnerabilities in infrastructure as code.

#### Secret Scanners:

* **`Gitleaks`**: imports scan results from [**Gitleaks Scanner** and **GitLab** **Gitleaks Scanner**](scanner-description/secret-scanners/gitleaks.md), which is a tool for finding secrets and sensitive information in _Git repositories_. It helps identify hard-coded secrets in Git repositories that are accidentally committed by developers.
* **`Trufflehog3`**: imports scan results from [**Trufflehog3 Scanner**](scanner-description/secret-scanners/trufflehog3.md), which is a tool for finding secrets and sensitive information in _code repositories_. Trufflehog3Importer converts the scan results into a format that can be easily understood by AppSec Portal.

**Image and code dependency scanners:**

* **`Trivy`**: imports scan results from [**Trivy Scanner**](scanner-description/image-and-code-dependency-scanners/trivy.md), which is a tool for finding security issues in Docker images and code repositories.&#x20;
* **`Vulners Trivy`**: imports scan results from [**Trivy Scanner with vulners.com**](scanner-description/image-and-code-dependency-scanners/trivy-vulners.com-plugin.md) plugin.&#x20;

#### Web Scanners:

* **`Arachni`**: imports scan results from [**Arachni Scanner**](scanner-description/web-scanners/arachni-scan.md), which is a tool for scanning modern web applications for a variety of vulnerabilities including SQL injection, cross-site scripting, file inclusion, and more.
* **`Acunetix`** : imports scan results from [**Acunetix**](scanner-description/web-scanners/acunetix.md), a scanner designed to detect vulnerabilities in web applications.
* **`Burpsuit`**: imports scan results from [**BurpSuit Enterprise scanner**](scanner-description/web-scanners/burp-enterprise-scan.md), which is a tool for automated web application security testing and vulnerability scanning.
* **`OWASP Zap`**: is responsible for importing scan results from [**GitLab** **OWASP Zap Scanner**](scanner-description/web-scanners/owasp-zap.md), wich is a security testing tool focused on web application vulnerabilities, including SQL injection, cross-site scripting (XSS), and more.

**Mobile Scanners:**

* **`Mobsfscan`**: is a security testing tool focused on mobile application vulnerabilities. [**This scanner**](scanner-description/mobile-security-scanners/mobsfscan.md) is based on **`Semgrep`** with custom rules from MobSF group

**Infrastructure scanners:**

* **`AWSSecurity`:** imports scan results from [**AWS Security Hub Scan**](scanner-description/infrastructure-scanners/aws-security-hub-scan/)**,** which is a powerful tool designed to analyze and identify potential security vulnerabilities in AWS environments. With this importer, you can seamlessly integrate AWS Security Hub scan results into the AppSec Portal, allowing for centralized management and comprehensive visibility of your security posture within the AWS ecosystem.
* **`Nuclei`**: imports scan results from [**Nuclei Scanner**](scanner-description/infrastructure-scanners/nuclei.md), which is a tool for finding security issues in web applications.
* **`Prowler`**: is responsible for importing scan results from the [**Prowler Scanner**](scanner-description/infrastructure-scanners/prowler.md). Prowler is a security scanning tool specifically designed to assess the security of Amazon Web Services (AWS) environments.&#x20;
* **`Subfinder`**: imports scan results from [**Subfinder Scanner**](scanner-description/infrastructure-scanners/subfinder.md). Subfinder is a subdomain discovery tool used to identify subdomains associated with a target domain or web application. It assists in gathering critical information during enumeration phases of security assessments and penetration testing.

#### Other scanners:

* **`GitLab SAST Report`** : imports results from [**Find Security Bugs Scan (GitLab SAST Report)**](scanner-description/other-scanners/gitlab-sast-report.md). This tool performs a static analysis of the application source code, identifying potential vulnerabilities and security issues.
* **`Manual`**
* **`Pen test`** : imports results from [**Pen test scanner**](scanner-description/other-scanners/pen-test.md). Processes the data from a report that describes the results of penetration testing performed, the purpose of which is to assess the security of a system or application by actively testing, identifying vulnerabilities, and providing recommendations for remediation of the problems found.
* **`Snyk:`** imports result from [**Snyk**](scanner-description/other-scanners/snyk.md) tool. Snyk is a platform that allows you to scan, prioritize, and fix security vulnerabilities in your code, open-source dependencies, container images, and infrastructure as code configurations.
* **`Whitespots Portal`** : imports results from [**Whitespots Portal scanner**](scanner-description/other-scanners/whitespots-portal.md). Processes the data that the user has specified in the scanner report.
