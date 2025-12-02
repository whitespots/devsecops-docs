# Microsoft SSO

{% hint style="warning" %}
The following steps describe the state of Microsoft services at the time of creating this instruction (16/01/2024).\
The Microsoft identity platform **interface may change**, so for the most up-to-date information, refer to the official [source](https://learn.microsoft.com/en-us/entra/identity-platform/scenario-web-app-call-api-overview) and their official [video guide](https://www.youtube.com/watch?v=LRoc-na27l0)
{% endhint %}

To log in to the AppSec portal through your Microsoft identity platform, follow these steps:

1. Navigate to your **Microsoft Entra** using the [link](https://entra.microsoft.com/#view/Microsoft_AAD_RegisteredApps/ApplicationsListBlade/quickStartType~/null/sourceType/Microsoft_AAD_IAM)
2. Navigate to **Application** -> **App registrations** section and **register a new** **application**

<figure><img src="../../../.gitbook/assets/micr sso1.png" alt=""><figcaption></figcaption></figure>

3. You will see the following screen, where you need to copy the \<Application (client) ID>:

<figure><img src="../../../.gitbook/assets/micr sso2.jpg" alt=""><figcaption><p><strong>Client ID</strong></p></figcaption></figure>

4. Now create a client secret on the "Certificates & secrets" tab:

<figure><img src="../../../.gitbook/assets/micr sso3.jpg" alt=""><figcaption><p><strong>Client Secret</strong></p></figcaption></figure>

5. The final data you have to get here is the **server metadata url.**

<figure><img src="../../../.gitbook/assets/micr sso metadata1.jpg" alt=""><figcaption><p><strong>Server metadata url</strong></p></figcaption></figure>

Use the data created for your application to [configure ](./)SSO integration in the AppSec portal:

* **Domain**: login.microsoftonline.com
* **Client ID**: \<Application (client) ID>
* **Client Secret**: \<Value>
* **Server metadata url**: \<OpenID Connect metadata document>

<figure><img src="../../../.gitbook/assets/SSO Microsoft values.jpeg" alt=""><figcaption><p>Microsoft SSO values example</p></figcaption></figure>

### MS Role Mapping

To create a role mapping in our portal, follow these steps:

1. **Create custom roles for Application**

Navigate to **Applications** -> **App registrations** -> <_**Created application**_> -> **App roles** section and create all required roles here

<figure><img src="../../../.gitbook/assets/micr sso4.jpg" alt=""><figcaption></figcaption></figure>

2. Now you will be able to assign users/groups to Application roles

<figure><img src="../../../.gitbook/assets/micr sso5.jpg" alt=""><figcaption></figcaption></figure>

For example select a group with all colleagues from IT department and assign them to our newly created role

<figure><img src="../../../.gitbook/assets/micr sso6.jpg" alt=""><figcaption></figcaption></figure>

3. [Configure](./#role-mapping) the mapping of roles for your SSO connection. \
   **JSON key in JWT token with list of external groups** field should equal to **roles** for this integration.&#x20;

{% hint style="danger" %}
The integration only works with the **roles** value\
We know that Microsoft provides the guide with a clearly displayed "groups" key 🤷‍♂️ \
Get more information about this specific feature from the [video](https://youtu.be/LRoc-na27l0?si=VBqZ1hvDWjUSpKmr)
{% endhint %}

<figure><img src="../../../.gitbook/assets/ms mapp.png" alt=""><figcaption></figcaption></figure>

3. If a mapping has not been previously configured, the first time you log in using Single Sign-On (SSO), the SSO settings will display a list of roles received from Microsoft under the name **External Group Name**. You can configure these roles by creating mappings. To do this, add the corresponding portal roles for each group from this list. <br>

If new roles appear on the Microsoft's side, they will also appear as unassociated during the first login and you should associate them later.

<figure><img src="../../../.gitbook/assets/micr sso8.png" alt=""><figcaption></figcaption></figure>
