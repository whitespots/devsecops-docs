---
description: >-
  Semgrep is a fast, open-source tool that scans source code to find programming
  errors, security vulnerabilities, and policy violations.
---

# Semgrep

**Auditor Job Name**: Semgrep, Gitlab Semgrep, Gitlab Php\
**Auditor image:** \
`registry.gitlab.com/whitespots-public/security-images/semgrep:1.74.0`\
`registry.gitlab.com/whitespots-public/security-images/semgrep-sast-gitlab:4`\
**AppSec Portal Importer Name**: Semgrep JSON Report, [GitLab Semgrep](https://gitlab.com/gitlab-org/security-products/analyzers/semgrep)

[Semgrep](https://github.com/semgrep/semgrep) supports several programming languages such as:

* Python
* JavaScript
* Java
* Go
* Ruby
* TypeScript
* C#
* Kotlin
* PHP
* Swift

The Semgrep can be used to scan for security issues such as:

* SQL injection
* Cross-site scripting (XSS)
* Command injection
* Authentication and authorization issues
* Insecure cryptography
* Code injection
* Path traversal
* File inclusion
* Information leakage
* XML external entity injection (XXE)
* Server-side request forgery (SSRF)
* and more

One interesting feature of Semgrep is its ability to detect security issues in **complex codebases**. It uses a powerful pattern-matching engine to identify vulnerabilities and is highly customizable.

#### Curl example&#x20;

{% code overflow="wrap" %}
```
curl -X POST localhost/api/v1/scan/import/ -H "Authorization: Token a75bb26171cf391671e67b128bfc8ae1c779ff7b" -H "Content-Type: multipart/form-data" -F "file=@./" -F "product_name=Product1" -F "product_type=Application" -F "scanner_name=Semgrep JSON Report" -F "branch=dev" -F "repository=git@gitlab.com:whitespots-public/appsec-portal.git"
```
{% endcode %}

In this command, the following parameters are used:

1. `-X POST`: specifies the HTTP method to be used (in this case, POST)
2. `-H "Authorization: Token <authorization_token>"`: specifies the [**authorization token**](../../importing-reports-from-scanners-to-appsec-portal/#authorization-token) obtained from AppSec Portal.
3. `-H "Content-Type: multipart/form-data"`: specifies the content type of the request.
4. `-F "file=@<report_file_path>"`: specifies the **path to the report file** generated by the scanner.
5. `-F "product_name=<product_name>"`: specifies the **name of the product** being scanned.
6. `-F "product_type=<product_type>"`: specifies the **type of the product** being scanned.
7. `-F "scanner_name=<scanner_name>"`: specifies the **name of the scanner** used to generate the report (Semgrep JSON Report or GitLab Semgrep)
8. `-F "branch=<branch_name>"`: (_optional_) specifies the name of the branch in the source code repository (if applicable) This parameter is particularly useful when you want to associate the scan results with a specific branch in your repository. If not provided, the scan will be associated with the default branch

Asset information, if an [auditor ](broken-reference)is used

9. `-F "repository=<repository SSH URL>"`: If your product is **code** in a repository enter the address of your **repository** in a specific format, for example: git@gitlab.com:whitespots-public/appsec-portal.git
10. &#x20;`-F "docker_image=<registry address>"`: If your product is **image** enter the address of the **registry** where your product is located, for example: registry.gitlab.com/whitespots-public/appsec-portal/back/auto\_validator:latest
11. `-F "domain=<domain>"`: If your product is **web** enter the **domain name** of your product, for example: whitespots.io
12. `-F "host=<host>"`: If your product is **web** enter the **IP address** of your product, for example: 0.0.0.0

**Report example:**

<figure><img src="../../../../../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>
