# Import Repositories

You can create products on the AppSec Portal by importing them from your GitHub or GitLab repositories

1. Navigate to the Assets page and click **Import Repositories**

<figure><img src="../../../.gitbook/assets/image (153).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (154).png" alt=""><figcaption></figcaption></figure>

2. **Select Code Management System** - GitLab or GitHub

<figure><img src="../../../.gitbook/assets/prod import2.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Importing from GitHub is only possible for organisation repositories.
{% endhint %}

3. Create an **Access Token** in the Code Management System and enter its value in the corresponding field

<figure><img src="../../../.gitbook/assets/prod import 3.png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
For a successful connection with the repository, the Access Token must have \
**scopes granted**: \
**GitHub** - <mark style="color:blue;">**`repo`**</mark>, <mark style="color:blue;">**`read:user`**</mark> and <mark style="color:blue;">**`user:email`**</mark> \
**GitLab** - <mark style="color:blue;">**`read_api`**</mark>
{% endhint %}

4. If your repository is hosted on **self-hosted instances** of GitHub or GitLab, enter their address and click **Next**

<figure><img src="../../../.gitbook/assets/prod import 4.png" alt=""><figcaption></figcaption></figure>

5. [**Create** ](product-creation.md)or **select** from the drop-down list an already created **product** for the desired repository and click **Submit**

<figure><img src="../../../.gitbook/assets/prod impor5.gif" alt=""><figcaption></figcaption></figure>

6. Congratulations! Your product and its asset repository have been created on the portal\
   You can [run an audit](broken-reference) immediately or set up an [Auditor schedule](broken-reference) for this product\


<figure><img src="../../../.gitbook/assets/prod import 7.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
For your convenience, **archived** repositories are labelled accordingly

<img src="../../../.gitbook/assets/prod import 6.png" alt="" data-size="original">
{% endhint %}
