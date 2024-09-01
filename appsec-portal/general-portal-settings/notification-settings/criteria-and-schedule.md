# Criteria & Schedule

Use the filter in the All Findings section to set the criteria for which findings notifications are sent and the frequency of notifications. \
You can set up multiple notification types for a single service

1. Navigate to the **All Findings** section and click the **Filters** button:

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/notif sched2.png" alt=""><figcaption></figcaption></figure>

2. In the filter settings, you can **select** the **criteria** by which to filter the **findings**, and these specific findings will be included in the notifications.

<figure><img src="../../../.gitbook/assets/notif sched 3.png" alt=""><figcaption></figcaption></figure>

3. **Create** the **schedule** for **sending notifications** by clicking the **Schedule** button at the bottom of the Filter window.

<figure><img src="../../../.gitbook/assets/notif sched4.png" alt=""><figcaption></figcaption></figure>

4. Configure a schedule to set the frequency of sending notifications\
   fill in the fields:

* **Title**: the name you have chosen for this schedule
* **Webhook**: select the previously configured integration from the drop-down list

{% hint style="warning" %}
The **name** in the **Title** should be **unique** and not repeat previously created schedule titles
{% endhint %}

<figure><img src="../../../.gitbook/assets/notif sched 5.png" alt=""><figcaption></figcaption></figure>

* **Crontab**: click on the **Set Schedule** button and select a frequency

<figure><img src="../../../.gitbook/assets/notif sched5.gif" alt=""><figcaption></figcaption></figure>

<mark style="background-color:blue;">The schedule is set and integrated into your service.</mark> \
From now on, Appsec Portal will send notifications with information about findings that match the selected criteria and at the set frequency.

<figure><img src="../../../.gitbook/assets/notif sched 6.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/notif sched 7.png" alt=""><figcaption><p>notification example</p></figcaption></figure>
