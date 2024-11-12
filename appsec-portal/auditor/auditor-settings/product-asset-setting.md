# Product Asset Setting

{% hint style="warning" %}
To ensure the proper functioning of Auditor, include assets for products created in the Portal in version v23.10.1 and earlier.
{% endhint %}

If the product has already been [created](../../general-portal-settings/product-settings/), add its Asset data. To do this, select the product on the Product page

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Specify the location of the product by adding <img src="../../../.gitbook/assets/image (133).png" alt="" data-size="line">  information about:

* [**Repository**](product-asset-setting.md#repository): to analyse the product <mark style="color:blue;">code</mark> in the repository
* [**Docker image**](product-asset-setting.md#docker-image): to analyse your <mark style="color:blue;">image</mark>
* [**Domain or Host**](product-asset-setting.md#domain-and-host): to analyse your <mark style="color:blue;">web</mark> product
* [**Cloud Account:**](product-asset-setting.md#cloud-account) to analyse the product in a <mark style="color:blue;">cloud account</mark>

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Repository

In the Repository tab, fill in the required fields:

1. **Repository SSH URL**: enter the address of your repository in a specific format, for example: git@gitlab.com:whitespots-public/appsec-portal.git

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

1. **Repository Link config**: repository source link used to link the portal to your repository based on a created pattern

Select a [pre-created](../../general-portal-settings/repository-link-configs.md) pattern from the drop-down list or use the find a matching config function

<figure><img src="../../../.gitbook/assets/asset link.gif" alt=""><figcaption></figcaption></figure>

Or create a new pattern directly from this section

<figure><img src="../../../.gitbook/assets/link2.gif" alt=""><figcaption></figcaption></figure>

3. Save the created asset by clicking on the **Create** button

<figure><img src="../../../.gitbook/assets/asset rep 4.png" alt=""><figcaption></figcaption></figure>

## Docker Image

In the **Repository tab** enter the address of the **registry** where your product is located and click **Create**

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Domain & Host

In the **Domain tab** enter **domain name**, for example whitespots.io

In the **Host tab** enter **host IP**, for example 83.110.124.0

Click **Create**

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Cloud Account

In the **Cloud account tab** enter the **Cloud Account Name** where your product is located,  its **Cloud key ID** and **Cloud key secret** and click **Create**

<figure><img src="../../../.gitbook/assets/cloud.png" alt=""><figcaption></figcaption></figure>

Apply the created assets when using the[ **Auditor**](../../../auditor/run-audit/)
