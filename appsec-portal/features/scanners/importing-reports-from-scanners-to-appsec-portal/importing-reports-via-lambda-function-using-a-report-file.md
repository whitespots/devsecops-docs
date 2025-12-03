---
description: To send scanning data to AppSec Portal
icon: webhook
---

# Importing reports via Lambda Function using a Report File

You have the capability to import reports into the AppSec Portal using the provided function below.

<pre class="language-python"><code class="lang-python">import json
import urllib.request
import urllib3


def import_report(&#x3C;<a data-footnote-ref href="#user-content-fn-1">event</a>>):
    
    appsec_portal_api_token = "Token " + &#x3C;<a data-footnote-ref href="#user-content-fn-2">appsec portal api_key></a>
    
    while True:
        try:
            url = 'https://&#x3C;<a data-footnote-ref href="#user-content-fn-2">portal_address</a>>/api/v1/scan/import/'
            body = {
                "file": ("&#x3C;<a data-footnote-ref href="#user-content-fn-1">event</a>>.json", json.dumps(&#x3C;<a data-footnote-ref href="#user-content-fn-1">event</a>>)),
                "product_name": "&#x3C;<a data-footnote-ref href="#user-content-fn-1">product name</a>>",
                "product_type": "&#x3C;<a data-footnote-ref href="#user-content-fn-1">product_type</a>>",
                "scanner_name": "&#x3C;<a data-footnote-ref href="#user-content-fn-1">scanner name</a>>",
                "branch": "<a data-footnote-ref href="#user-content-fn-1">&#x3C;branch_name></a>", 
                "repository": "&#x3C;<a data-footnote-ref href="#user-content-fn-1">repository SSH URL</a>>",
                "docker_image": "&#x3C;<a data-footnote-ref href="#user-content-fn-1">registry address</a>>", 
                "domain": "&#x3C;<a data-footnote-ref href="#user-content-fn-1">domain</a>>", 
                "host": "&#x3C;<a data-footnote-ref href="#user-content-fn-1">host</a>>"
            }
            data, header = urllib3.encode_multipart_formdata(body)
            r = urllib.request.Request(url, data=data)
            r.add_header('Authorization', appsec_portal_api_token)
            r.add_header('Content-Type', header)
            response = urllib.request.urlopen(r)
            print(response.getcode())
        except Exception as e:
            raise e
        break
    return {
        'statusCode': 200,
        'body': json.dumps('Event successfully imported')
    }
</code></pre>

Replace the following parameters:

* _**\<event>**_ with the name of your file containing report
* _**\<appsec portal api key>**_ with the key of your [**authorization token**](./#authorization-token)
* &#x20;**\<portal address>** with the address of your AppSec Portal
* **\<product name>** with the name of your product
* &#x20;**\<product\_type>** with the name of your product type
* &#x20;**\<scanner name>** with the [**name of your scanner**](../scanner-description/)
* **\<branch>** (_optional_) with the the name of the branch in the source code repository (if applicable) This parameter is particularly useful when you want to associate the scan results with a specific branch in your repository. If not provided, the scan will be associated with the default branch

Asset information, if an [auditor ](../../../../auditor/)is used

* **\<repository>**&#x49;f your product is **code** in a repository enter the address of your **repository** in a specific format, for example: git@gitlab.com:whitespots-public/appsec-portal.git
* **\<docker\_image>** If your product is **image** enter the address of the **registry** where your product is located, for example: registry.gitlab.com/whitespots-public/appsec-portal/back/auto\_validator:latest
* **\<domain>** If your product is **web** enter the **domain name** of your product, for example: whitespots.io
* **\<host>** If your product is **web** enter the **IP address** of your product, for example: 0.0.0.0

Congratulations!🎉  Your function is now ready to send reports to AppSec Portal

[^1]: replace

[^2]: replace&#x20;
