# CVSS Rule

Set up a rule to **automatically** rate your products by following the steps below.

1. Navigate to the CVSS section and click on the **Create Rule** button
2. In the window that opens, select the **products** to which you want the rules to apply, or leave the default setting to include all your products.

<figure><img src="../../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/cvss2-1.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/cvss2(1).png" alt=""><figcaption></figcaption></figure>

3. Add the CVSS vector value

<figure><img src="../../../../.gitbook/assets/cvss3.png" alt=""><figcaption></figcaption></figure>

3.1 Select the **version** of the standard and the **values of the metrics** in groups by clicking on the corresponding fields

{% hint style="success" %}
For more information on the metrics of the [3.1](https://www.first.org/cvss/v3.1/specification-document) and [4.0](https://www.first.org/cvss/v4.0/specification-document) versions of the standard, please refer to the [official documentation](https://www.first.org/cvss/)
{% endhint %}

<figure><img src="../../../../.gitbook/assets/cvss4.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
In version 3.1, users can **adjust** **all baseline metrics** within the Environmental metrics group to their modified counterparts. This feature allows for the customization of metric values based on a component's specific role within an organization's infrastructure.
{% endhint %}

4. Select a parameter(s) and enter its value. This rule will be applied to the findings corresponding to these parameters and their values.

Available parameters:

* title
* description&#x20;
* file path&#x20;
* branch
* scanner&#x20;
* dependency&#x20;
* vulnerable url&#x20;
* import source

5. Click Submit

<figure><img src="../../../../.gitbook/assets/cvss6.png" alt=""><figcaption></figcaption></figure>

5. The rule will be created and the CVSS value will be automatically assigned to the corresponding findings when processing the scan results.&#x20;

You can disable the application of these rules at any time by toggling the Active slider.

<figure><img src="../../../../.gitbook/assets/cvss6(1).png" alt=""><figcaption></figcaption></figure>

