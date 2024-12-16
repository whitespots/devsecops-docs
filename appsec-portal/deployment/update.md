---
description: How to update AppSec Portal
---

# Update

* [**GitLab CI update**](update.md#option-1.-update-using-gitlab-ci)
* [**Update using Helm**](update.md#update-using-helm)
* [**Manual update**](update.md#option-2.-manual-update)



To update the AppSec Portal to the latest version, follow these steps:

### Update using GitLab CI

1. [Update](https://docs.gitlab.com/ee/user/project/repository/mirror/index.html) your forked repository
2. Run pipeline
3. Click on **update** section

<figure><img src="../../.gitbook/assets/pipeline.png" alt=""><figcaption></figcaption></figure>

### Update using helm <a href="#update-using-helm" id="update-using-helm"></a>

1. To update, run the following command:

<pre><code>helm repo update appsecportal
<strong>helm upgrade appsecportal appsecportal/appsecportal
</strong></code></pre>

`helm repo update appsecportal`: This command gets the latest Helm package from the repository, ensuring that you have the latest version.

`helm upgrade appsecportal appsecportal/appsecportal`: This command upgrades your application to the latest version. If any variables <mark style="background-color:blue;">have been changed since installation</mark>, you <mark style="background-color:blue;">must specify them again in this command</mark> to ensure that they are applied correctly.

### **Manual update**

1. Pull the latest changes from the repository:

```bash
git pull
```

2. Edit `IMAGE_VERSION` variable in .env file&#x20;
3. Pull images

```
docker compose pull
```

4. Restart your app

<pre><code><strong>docker compose down -v &#x26;&#x26; docker compose up -d
</strong></code></pre>

This will stop all services and remove the associated volumes, which will clean up the environment.

That's it.&#x20;

Portal will care about all migrations :smile:

