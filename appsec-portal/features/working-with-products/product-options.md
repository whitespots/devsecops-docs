# Product options

Product options are accessed by selecting a product from the **Product** tab and navigating to the **Options** tab.

<figure><img src="../../../.gitbook/assets/image (155).png" alt=""><figcaption></figcaption></figure>

\
On the Product options page, you can specify **Product related tags**, change the **Product type**, specify the product as the **default product** (default product will be used for reports import functionality if no specific product has been provided) and view the current data of **Jira integration settings** sourced from the [global integration settings](../jira/jira-integration-configuration.md#step-3.-default-team-spaces) with Jira.&#x20;

**Jira integration settings** are displayed here to provide you with an overview of the Jira configuration that has been set up on a global level. Any changes made to the Jira configuration at the product level will be specific to this product and will override the global settings for the integration.

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

The **Product related tags** field allows you to create and add tags to the findings that are related to this specific product in AppSec Portal. And also to filter products by these tags.

<figure><img src="../../../.gitbook/assets/product related tag jira.png" alt=""><figcaption></figcaption></figure>

The **Push tags to Jira tasks** toggle button enables the tags from the Product Related Tags field to be sent to the corresponding Jira tasks after the finding has been verified in the portal.

To send the product title to the corresponding Jira product tasks as task labels, activate the **Push product title to Jira task labels** toggle button.

{% hint style="info" %}
When labels are added to a task in Jira, they will appear as tags in the corresponding findings in the AppSec Portal **when the** [**Jira webhook**](../jira/setting-up-jira-webhook.md) **is activated** (e.g. when the task name is changed).
{% endhint %}

Finally, if you wish to **delete** a product from AppSec Portal, you can do so from the Product options page.
