# Product Asset

{% hint style="warning" %}
To ensure the proper functioning of Auditor, include assets for products created in the Portal in version v23.10.1 and earlier.
{% endhint %}

To enable [**Auditor** ](broken-reference)functionality, it is necessary to define the product asset by indicating the **product's location**.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

Specify the location of the product by adding <img src="../../../.gitbook/assets/image (133).png" alt="" data-size="line">  information about:

* [**Repository**](product-asset.md#repository): to analyse the product <mark style="color:blue;">code</mark> in the repository
* [**Docker image**](product-asset.md#docker-image): to analyse your <mark style="color:blue;">image</mark>
* [**Domain or Host**](product-asset.md#domain-and-host): to analyse your <mark style="color:blue;">web</mark> product
* Cloud account: to analyse <mark style="color:blue;">cloud account</mark>

<figure><img src="../../../.gitbook/assets/assets.gif" alt=""><figcaption></figcaption></figure>

## Repository

In the Repository tab, fill in the required fields:

1. **Repository SSH URL**: enter the address of your repository in a specific format, for example: git@gitlab.com:whitespots-public/appsec-portal.git

<figure><img src="../../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

1. **Repository Link config**: repository source link used to link the portal to your repository based on a created pattern

Select a [pre-created](../repository-link-configs.md) pattern from the drop-down list or use the find a matching config function

<figure><img src="../../../.gitbook/assets/repos asset 2.gif" alt=""><figcaption></figcaption></figure>

Or create a new pattern directly from this section

<figure><img src="../../../.gitbook/assets/repos 3(1).gif" alt=""><figcaption></figcaption></figure>

3. Save the created asset by clicking on the **Create** button

<figure><img src="../../../.gitbook/assets/asset rep 4.png" alt=""><figcaption></figcaption></figure>

## Docker Image

In the **Docker Image tab** enter the address of the **registry** where your product is located and click **Create**

<figure><img src="../../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

## Domain & Host

In the **Domain tab** enter **domain name**, for example whitespots.io

In the **Host tab** enter **host IP**, for example 83.110.124.0

Click **Create**

<figure><img src="../../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

## Cloud Account

In the **Cloud Account tab** enter the address of the **cloud account name, Cloud key ID** and **Cloud key secret** where your product is located and click **Create**

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Apply the created assets when using the[ **Auditor**](../../../auditor/run-audit/)
