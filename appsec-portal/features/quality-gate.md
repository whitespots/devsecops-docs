---
icon: dungeon
---

# Quality Gate

## Pre requirement

You have to setup the integration with your version control ([guide](../general-portal-settings/version-control-integration.md))

## How to put comments on merge requests

1. Navigate to Settings->Integrations->Version Control-> \<your version control system>
2. Scroll to the bottom

<figure><img src="../../.gitbook/assets/image.png" alt="" width="375"><figcaption></figcaption></figure>

There are some usefull settings here. Take a deep look, if you want this quality gate to be applied to products with specific business criticality/verified or just critical vulnerabilities

<figure><img src="../../.gitbook/assets/image (1).png" alt="" width="375"><figcaption></figcaption></figure>

General filters example:

<figure><img src="../../.gitbook/assets/image (2).png" alt="" width="375"><figcaption></figcaption></figure>

This is a **general** filter, which means that there's a functionality to setup an own filter for each action as well.

We don't recommend beginners to setup additional filters, because there might be some misunderstanding about "absent" comments.

<figure><img src="../../.gitbook/assets/image (3).png" alt="" width="375"><figcaption></figcaption></figure>

Summary comment example:

<figure><img src="../../.gitbook/assets/image (9).png" alt="" width="375"><figcaption></figcaption></figure>

## How to block merge requests

Another question, that we usually get is "how to kill the pipeline if there are verified vulnerabilities?"

There's no need to kill something. You are free to just close merge request with additional comment to let developers know, that they won't merge their changes until they fix vulnerabilities.

> It's better to set up comments first, then test auto closer with resolve action for your scanners and block merge requests only after that

<figure><img src="../../.gitbook/assets/image (4).png" alt="" width="375"><figcaption></figcaption></figure>



## I need a job in CI/CD for devops team

We have seen some clients with this feature request, so maybe you want it too :smile:

If your DevOps team wants CI semaphore - you can enable it&#x20;

<figure><img src="../../.gitbook/assets/image (5).png" alt="" width="188"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (6).png" alt="" width="375"><figcaption></figcaption></figure>
