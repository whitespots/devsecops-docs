# 📊 Jira

## How to configure:

* **Step 1:**  [**Portal -> Jira**](jira-integration-configuration.md)
* **Step 2:** [**Jira -> Portal**](setting-up-jira-webhook.md)

## Summary

AppSec Portal provides **bi-directional** integration with **Jira**.

{% hint style="info" %}
Developers spaces may have their own required _custom fields_ like **Sprint** or **Component**. If there were such space in your company, you would be not able to create a task there directly. \
In such case many companies create another space _without any restrictions_ in workflow and required custom fields — **security space**.
{% endhint %}

✅ We support 2 Jira spaces: **security** and **product**. \
✅ Synchronise tasks, comments and updates between the security and product spaces for more convenience! It means, that you can put any comment in **product** task and it will appear in **security** task. \
… and it works **in both directions**.\
✅ There is an option to set _default_ security space and _default_ product space to save time from configuring them in product settings. \
✅ You may set _specific_ product and security space in product setting if it's necessary.

## Why Webhook?

The portal supports both variants of integration (**with webhook** and **without** it) according to your needs. Webhook is required to **synchronise** **task statuses, assignees** and **tags** between spaces. Here you can see available features:

<table><thead><tr><th width="206.33333333333331">Feature</th><th width="255">without Webhook</th><th>with Webhook</th></tr></thead><tbody><tr><td>Create Jira task</td><td>✅</td><td>✅</td></tr><tr><td>Update Jira task</td><td>✅</td><td>✅</td></tr><tr><td>Delete Jira task</td><td>✅</td><td>✅</td></tr><tr><td>Sync between AppSec portal and security/product spaces:</td><td></td><td></td></tr><tr><td><ul><li>Tasks</li></ul></td><td>❌</td><td>✅</td></tr><tr><td><ul><li>Statuses</li></ul></td><td>❌</td><td>✅</td></tr><tr><td><ul><li>Priority (severity)</li></ul></td><td>❌</td><td>✅</td></tr><tr><td><ul><li>Assigned team</li></ul></td><td>❌</td><td>✅</td></tr><tr><td><ul><li>Comments</li></ul></td><td>❌ Only one way to Jira</td><td>✅</td></tr><tr><td><ul><li>Tags</li></ul></td><td>❌ Only one way to Jira</td><td>✅</td></tr></tbody></table>
