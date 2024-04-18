---
description: >-
  Setting up an Auditor's schedule and getting audit results at your desired
  time
---

# Scheduled Audit Run

1. From the Dashboard page navigate to Aditor -> Schedule

<figure><img src="../../../.gitbook/assets/sched 1.png" alt=""><figcaption></figcaption></figure>

2. Click on the **Task** in the right panel.

<figure><img src="../../../.gitbook/assets/sched 2 (1).png" alt=""><figcaption></figcaption></figure>

3. In the opened window, complete the following fields: **Title**, **Crontab**, **Job Sequence**, **Affected products**.\
   You can deactivate the schedule any time by toggling the **Active** slider.

<figure><img src="../../../.gitbook/assets/sched 3.png" alt=""><figcaption></figcaption></figure>

3.1 In the **Title** field enter the name of your schedule, e.g.:

<figure><img src="../../../.gitbook/assets/shed 4.png" alt=""><figcaption></figcaption></figure>

3.2 Click the _**Set Schedule**_ button in the **Crontab** field to customize the Auditor's run time.

<figure><img src="../../../.gitbook/assets/sched 5.png" alt=""><figcaption></figcaption></figure>

In the displayed calendar, set the Auditor's work:

* Periodicity: Monthly, Weekly or Daily
* The Date of the month or Day of the week for monthly and weekly frequency, respectively
* Time

Days and Times support multi-selection&#x20;

Click **Apply** to accept the configuration

{% tabs %}
{% tab title="Monthly frequency" %}
<figure><img src="../../../.gitbook/assets/sched mon 1 (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Weekly frequency" %}
<figure><img src="../../../.gitbook/assets/sched week(1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Daily frequency" %}
<figure><img src="../../../.gitbook/assets/sched daily 1.png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

The selected time will be displayed in the field in the format \*\*\*\*\*, where&#x20;

<figure><img src="../../../.gitbook/assets/sched contr.JPG" alt=""><figcaption><p>Your schedule is set up for audits every Monday and Thursday at 8:00 a.m. and 3:00 p.m.</p></figcaption></figure>

3.3 For **Job Sequence**, choose from the drop-down list.

<figure><img src="../../../.gitbook/assets/sched 6.png" alt="" width="375"><figcaption></figcaption></figure>

3.4 **Affect products**:&#x20;

* All your products are automatically added to the schedule. You can also select product tags and all products with the selected tags will be included in the auditor's processing.

<figure><img src="../../../.gitbook/assets/afected prod sched1.gif" alt=""><figcaption></figcaption></figure>

* Or select **specific products** by clicking **Edit** and choosing particular products.

<figure><img src="../../../.gitbook/assets/affect prod shed2.gif" alt=""><figcaption></figcaption></figure>

4. Click **Create**

<figure><img src="../../../.gitbook/assets/sched9 (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The audit is run on all the assets that are set up in the selected products
{% endhint %}

If necessary, you can change the settings in the created task. \
You can also include all current and future products in the schedule.

<figure><img src="../../../.gitbook/assets/sched.png" alt=""><figcaption></figcaption></figure>

If global settings are selected in your schedule, you can specify a tag name so that the auditor only scans products with that tag.

{% hint style="warning" %}
This setting can only be made by users with a role that has access to all product types.
{% endhint %}

<figure><img src="../../../.gitbook/assets/auditor tag.gif" alt=""><figcaption></figcaption></figure>
