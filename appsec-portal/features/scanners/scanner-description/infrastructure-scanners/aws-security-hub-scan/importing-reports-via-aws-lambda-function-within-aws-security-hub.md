---
description: To send scanning data to AWS Security Hub on AppSec Portal
---

# Importing reports via AWS Lambda Function within AWS Security Hub

This is achieved using an AWS Lambda function written in Python. The function extracts an API key from AWS Secrets Manager, constructs a request with scanning data, and sends it to the specified AppSec Portal address.

## Step 1: Integration Preparation

1. AWS Lambda: Ensure you have a configured and functioning AWS Lambda function
2. AWS Secrets Manager: Create a secret in AWS Secrets Manager containing the [**API key**](../../../importing-reports-from-scanners-to-appsec-portal/#authorization-token) for accessing AppSec Portal. Ensure you have read access rights to this secret

## Step 2: Creating AWS Lambda Function

1. Navigate to the AWS Lambda console
2. Create a new Lambda function according to your requirements
3. Make sure the function has the necessary permissions to access Secrets Manager and make HTTP requests
4. Insert the code into the code editor of your function:

```python
import json
import boto3
import urllib.request
import urllib3


def lambda_handler(event, context):
    
    # Fetch AppSec Portal API key from AWS Secrets Manager
    client_sm = boto3.client('secretsmanager')
    appsec_portal_secret_raw = client_sm.get_secret_value(
        SecretId="<secret_name>"
    )
    appsec_portal_api_json = json.loads(appsec_portal_secret_raw["SecretString"])
    appsec_portal_api_token = "Token " + appsec_portal_api_json['key']
    
    while True:
        try:
            url = 'https://<portal_address>/api/v1/scan/import/'
            body = {
                "file": ("event.json", json.dumps(event)),
                "product_name": "AWS",
                "product_type": "AWS",
                "scanner_name": "AWS Security Hub Scan"
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
        'body': json.dumps('Hello from Lambda!')
    }
```

Replace "_**\<secret\_name>**_" with the name of the secret in AWS Secrets Manager containing your API key for AppSec Portal

Replace "_**\<portal\_address>**_" with the address of your AppSec Portal

5. Save the changes made to the function

## Step 3: Running the Function

1. In the "Test" section of the AWS Lambda console, create a test event with content similar to your report to test the function
2. If the function passes testing successfully, publish it

Congratulations! Your function is now ready to send reports to AppSec Portal

