---
description: >-
  Quickly find and fix the vulnerabilities that put your web applications at
  risk of attack.
---

# Acunetix

**AppSec Portal Importer Name**: Acunetix Scan

[Acunetix](https://www.acunetix.com/) is a specialized scanner designed to detect **vulnerabilities** in **web applications**. It provides a comprehensive solution for identifying security issues that could potentially compromise the security of web applications.

Acunetix scans web applications by performing a thorough examination of their code, configuration, and functionality. It is equipped to discover a wide range of security vulnerabilities, including but not limited to SQL injection, cross-site scripting (XSS), security misconfigurations, and more. This extensive coverage ensures that web application developers and security professionals can identify and address potential threats effectively.

#### Curl example

{% code overflow="wrap" %}
```
curl -X POST localhost/api/v1/scan/import/ -H "Authorization: Token a75bb26171cf391671e67b128bfc8ae1c779ff7b" -H "Content-Type: multipart/form-data" -F "file=@./acunetix.json" -F "product_name=Product1" -F "product_type=Application" -F "scanner_name= Acunetix Scan" -F "branch=dev" 
```
{% endcode %}

In this command, the following parameters are used:

1. `-X POST`: specifies the HTTP method to be used (in this case, POST)
2. `-H "Authorization: Token <authorization_token>"`: specifies the [**authorization token**](../../importing-reports-from-scanners-to-appsec-portal/#authorization-token) obtained from AppSec Portal.
3. `-H "Content-Type: multipart/form-data"`: specifies the content type of the request.
4. `-F "file=@<report_file_path>"`: specifies the **path to the report file** generated by the scanner.
5. `-F "product_name=<product_name>"`: specifies the **name of the product** being scanned.
6. `-F "product_type=<product_type>"`: specifies the **type of the product** being scanned.
7. `-F "scanner_name=<scanner_name>"`: specifies the **name of the scanner** used to generate the report (Acunetix Scan)
8. `-F "branch=<branch_name>"`: (_optional_) specifies the name of the branch in the source code repository (if applicable) This parameter is particularly useful when you want to associate the scan results with a specific branch in your repository. If not provided, the scan will be associated with the default branch
