---
description: >-
  CodeQL is a powerful static analysis tool for analyzing and finding security
  vulnerabilities in code.
---

# CodeQL

**AppSec Portal Importer Name**: CodeQL Scan (SARIF)

CodeQL uses a semantic code analysis engine to understand the behavior of code and find potential security issues, including **SQL injection**, **cross-site scripting**, and more. CodeQL can be used to analyze code written in a wide range of programming languages, including **C++**, **Java**, **Python**, and **JavaScript**, making it a versatile tool for any development team.

CodeQL works by creating a **graph database** that models the behavior of code. This database allows CodeQL to understand how different parts of the code interact with each other and identify potential security issues that may arise from those interactions. CodeQL also provides a range of powerful query languages that allow developers to write custom queries to find specific security issues or patterns in their code.

#### Curl example

{% code overflow="wrap" %}
```
curl -X POST localhost/api/v1/scan/import/ -H "Authorization: Token a75bb26171cf391671e67b128bfc8ae1c779ff7b" -H "Content-Type: multipart/form-data" -F "file=@./" -F "product_name=Product1" -F "product_type=Application" -F "scanner_name=CodeQL Scan (SARIF)" -F "branch=dev" 
```
{% endcode %}

In this command, the following parameters are used:

1. `-X POST`: specifies the HTTP method to be used (in this case, POST)
2. `-H "Authorization: Token <authorization_token>"`: specifies the [**authorization token**](../../importing-reports-from-scanners-to-appsec-portal/#authorization-token) obtained from AppSec Portal.
3. `-H "Content-Type: multipart/form-data"`: specifies the content type of the request.
4. `-F "file=@<report_file_path>"`: specifies the **path to the report file** generated by the scanner.
5. `-F "product_name=<product_name>"`: specifies the **name of the product** being scanned.
6. `-F "product_type=<product_type>"`: specifies the **type of the product** being scanned.
7. `-F "scanner_name=<scanner_name>"`: specifies the **name of the scanner** used to generate the report (CodeQL Scan (SARIF))
8. `-F "branch=<branch_name>"`: (_optional_) specifies the name of the branch in the source code repository (if applicable) This parameter is particularly useful when you want to associate the scan results with a specific branch in your repository. If not provided, the scan will be associated with the default branch

**Report example:**

```json
{
  "$schema": "https://json.schemastore.org/sarif-2.1.0.json",
  "version": "2.1.0",
  "runs": [
    {
      "tool": {
        "driver": {
          "name": "Tool Name",
          "rules": [
            {
              "id": "R01"
                      ...
              "properties" : {
                 "id" : "java/unsafe-deserialization",
                 "kind" : "path-problem",
                 "name" : "...",
                 "problem.severity" : "error",
                 "security-severity" : "9.8",
               }
            }
          ]
        }
      },
      "results": [
        {
          "ruleId": "R01",
          "message": {
            "text": "Result text. This result does not have a rule associated."
          },
          "locations": [
            {
              "physicalLocation": {
                "artifactLocation": {
                  "uri": "fileURI"
                },
                "region": {
                  "startLine": 2,
                  "startColumn": 7,
                  "endColumn": 10
                }
              }
            }
          ],
          "partialFingerprints": {
            "primaryLocationLineHash": "39fa2ee980eb94b0:1"
          }
        }
      ]
    }
  ]
}
```
