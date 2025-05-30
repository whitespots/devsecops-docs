# Dependency-Track

**AppSec Portal Importer Name**: Dependency-Track

[**Dependency-Track** ](https://github.com/DependencyTrack/dependency-track)is an intelligent Component Analysis platform that allows organizations to identify and reduce risk in the software supply chain.

#### Curl example

{% code overflow="wrap" %}
```
curl -X POST localhost/api/v1/scan/import/ -H "Authorization: Token a75bb26171cf391671e67b128bfc8ae1c779ff7b" -H "Content-Type: multipart/form-data" -F "file=@./mobsfscan.json" -F "product_name=Product1" -F "product_type=Application" -F "scanner_name=Dependency-Track" -F "branch=dev" 
```
{% endcode %}

In this command, the following parameters are used:

1. `-X POST`: specifies the HTTP method to be used (in this case, POST)
2. `-H "Authorization: Token <authorization_token>"`: specifies the [**authorization token**](../../importing-reports-from-scanners-to-appsec-portal/#authorization-token) obtained from AppSec Portal.
3. `-H "Content-Type: multipart/form-data"`: specifies the content type of the request.
4. `-F "file=@<report_file_path>"`: specifies the **path to the report file** generated by the scanner.
5. `-F "product_name=<product_name>"`: specifies the **name of the product** being scanned.
6. `-F "product_type=<product_type>"`: specifies the **type of the product** being scanned.
7. `-F "scanner_name=<scanner_name>"`: specifies the **name of the scanner** used to generate the report (Dependency-Track)
8. `-F "branch=<branch_name>"`: (_optional_) specifies the name of the branch in the source code repository (if applicable) This parameter is particularly useful when you want to associate the scan results with a specific branch in your repository. If not provided, the scan will be associated with the default branch

