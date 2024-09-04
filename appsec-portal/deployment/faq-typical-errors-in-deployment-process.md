# FAQ: typical errors in deployment process

Deployment of software applications is a critical process that ensures the application is available. However, there are many things that can go wrong during the deployment process. In this page, we will highlight some **common errors** that occur during deployment and provide **solutions** for resolving them.

### Keys without \n in Environment Variables

One common error that occurs during deployment is when keys (such as **`LICENSE_SERVER_PUBLIC_KEY`**, **`JWT_PRIVATE_KEY`**, and **`JWT_PUBLIC_KEY`**) are passed to environment variables without **`\n`** at the beginning and at the end, as specified in the [`docker-compose.yml`](https://gitlab.com/whitespots-public/appsec-portal/-/blob/main/docker-compose.yml) file. This error can lead to the following error message:

<figure><img src="../../.gitbook/assets/telegram-cloud-photo-size-2-5264822636184192889-y.jpg" alt=""><figcaption></figcaption></figure>

**Solution:**

To fix this error, make sure that all keys that are passed to environment variables have `\n` at **the beginning** and **at the end**, as shown in the following example (from `docker-compose.yml`):

{% code overflow="wrap" %}
```yaml
LICENSE_SERVER_PUBLIC_KEY:------BEGIN PUBLIC KEY-----\nMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA1FNL5uDzHbXyxgpTbVfE\nXtSn9yjo4wVRTllv8sUHmOCRfDWi7jMtRllIrZODbdPXy1qpfDAJjCw/8mRGR1QZ\nPPjUvcHT2cHFmYqjnO7jt3ywls8Sq+x2R6rG4EonKTWxJ27CoM6q8pl4z/Oqea9t\nwy9DQB9lTUipWLGGWenRtURt5YniGe6mLl/GFX1NVbDZOv7q+N/lHyBu/jFoWnnA\nfuqh9NzFM8yh+h81m+IXqFEU/4y9GRYHx2TKfCg36kYkEHF84DhV8DAiC+wmQbI5\nXNmlBHaW3yIiSnUWqC/QVlsdd8edXKh3pnpLsZ8+4Ni0+3+bV6UXtKUXD4oE2xAT\nvwIDAQAB\n-----END PUBLIC KEY-----
```
{% endcode %}

> If you have any issues during installation or have any questions about using our platform, don't hesitate to reach out to our support team _**sales@whitespots.io**_ :heart:.
