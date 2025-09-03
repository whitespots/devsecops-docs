# GitLab SSO

{% hint style="warning" %}
The following steps describe the state of GitLab at the time of creating this instruction. The GitLab interface may change, so for the most up-to-date information, refer to the official [source](https://docs.gitlab.com/ee/integration/openid_connect_provider.html)
{% endhint %}

To log in to the AppSec portal through your GitLab account, follow these steps:

1. Navigate to your **profile** settings in GitLab and select the "**Applications**" tab.
2. Click "**Add new application**"

<figure><img src="../../../.gitbook/assets/gitlab sso1.png" alt=""><figcaption></figcaption></figure>

3. Fill in the fields:&#x20;

* **Name** - Enter the name of the application as desired
* **Redirect URI** - _**https://portal-dev.whitespots.io/oauth2/callback**_&#x20;
* Ensure that the "**Confidential**" connection option is selected
* Choose the **scope** of information to be shared: _**openid**_, _**profile**_, _**email, read\_api (if you want to sync repositories)**_
* Click "**Save application**"

<figure><img src="../../../.gitbook/assets/gitlab sso2.gif" alt=""><figcaption></figcaption></figure>

Use the data created for your application to [configure ](./)SSO integration in the AppSec portal:

* **Domain**: gitlab.com
* **Client ID**: \<Application ID>
* **Client Secret**: \<Secret>
* **Scopes**: \<Scopes>

<figure><img src="../../../.gitbook/assets/gitlab sso2.png" alt=""><figcaption></figcaption></figure>

These settings will allow you to use your GitLab account to log in to the AppSec portal
