---
description: Open Source security tool to perform AWS, GCP and Azure security
---

# Prowler

**Auditor Job Name**: Prowler AWS\
**Auditor image:** registry.gitlab.com/whitespots-public/security-images/prowler:3.11.3\
**AppSec Portal Importer Name**: Prowler

[**Prowler**](https://docs.prowler.pro/en/latest/) is a security scanning tool designed for assessing security and identifying potential vulnerabilities within **Amazon Web Services** (AWS) infrastructure and resources. This tool is developed to assist organizations and security engineers in detecting and addressing threats and vulnerabilities in their AWS environment.&#x20;

Prowler enables the scanning of various types of AWS resources, including virtual machines, data storage, databases, and more.

#### Curl example

{% code overflow="wrap" %}
```
curl -X POST localhost/api/v1/scan/import/ -H "Authorization: Token a75bb26171cf391671e67b128bfc8ae1c779ff7b" -H "Content-Type: multipart/form-data" -F "file=@./prowler.json" -F "product_name=Product1" -F "product_type=Application" -F "scanner_name=Prowler" -F "branch=dev" -F "repository=git@gitlab.com:whitespots-public/appsec-portal.git"
```
{% endcode %}

In this command, the following parameters are used:

1. `-X POST`: specifies the HTTP method to be used (in this case, POST)
2. `-H "Authorization: Token <authorization_token>"`: specifies the [**authorization token**](../../importing-reports-from-scanners-to-appsec-portal/#authorization-token) obtained from AppSec Portal.
3. `-H "Content-Type: multipart/form-data"`: specifies the content type of the request.
4. `-F "file=@<report_file_path>"`: specifies the **path to the report file** generated by the scanner.
5. `-F "product_name=<product_name>"`: specifies the **name of the product** being scanned.
6. `-F "product_type=<product_type>"`: specifies the **type of the product** being scanned.
7. `-F "scanner_name=<scanner_name>"`: specifies the **name of the scanner** used to generate the report (Prowler)
8. `-F "branch=<branch_name>"`: (_optional_) specifies the name of the branch in the source code repository (if applicable) This parameter is particularly useful when you want to associate the scan results with a specific branch in your repository. If not provided, the scan will be associated with the default branch

Asset information, if an [auditor ](broken-reference)is used

9. `-F "repository=<repository SSH URL>"`: If your product is **code** in a repository enter the address of your **repository** in a specific format, for example: git@gitlab.com:whitespots-public/appsec-portal.git
10. &#x20;`-F "docker_image=<registry address>"`: If your product is **image** enter the address of the **registry** where your product is located, for example: registry.gitlab.com/whitespots-public/appsec-portal/back/auto\_validator:latest
11. `-F "domain=<domain>"`: If your product is **web** enter the **domain name** of your product, for example: whitespots.io
12. `-F "host=<host>"`: If your product is **web** enter the **IP address** of your product, for example: 0.0.0.0