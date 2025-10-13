# Bring your own scanner

> **If your scanner generates json - we support it**

## Requirements

1. Json report as an example for us to parse it
2. Docker image with scanner



## Add job to auditor

1. Navigate to Auditor->Jobs
2. Find a button on the right to create a new job

<figure><img src="../../.gitbook/assets/image (11).png" alt="" width="375"><figcaption></figcaption></figure>

There are a lot of settings for jobs. If you find that hard to understand - take a look at any of our existing jobs

<figure><img src="../../.gitbook/assets/image (12).png" alt="" width="375"><figcaption></figcaption></figure>



Ok, you put the image address, now it's time to describe how it works

<figure><img src="../../.gitbook/assets/image (13).png" alt="" width="375"><figcaption></figcaption></figure>



## Add a new importer

1. Navigate to Settings->Scanners
2. Create a new importer with preferable name

<figure><img src="../../.gitbook/assets/image (14).png" alt="" width="375"><figcaption></figcaption></figure>

3. Go inside this scanner to configure the parse logic

<figure><img src="../../.gitbook/assets/image (15).png" alt="" width="375"><figcaption></figcaption></figure>

4. Carefully follow the instructions (watch the video for more details)

{% file src="../../.gitbook/assets/How to add custom scanners.mp4" %}

> <mark style="color:$danger;">**Important information**</mark>
>
> Not all scanners have CWE, some of them don't provide recommendations (as in example), only a few have proper severity table. That's normal for them. You may tweak it with portal. That's why we eat our bread :smile:

:tada: That's it. Now you can get back to auditor and set a new SCAN\_TYPE variable.&#x20;

Put your job in a sequence and enjoy new checks.

PS. don't forget to create a rule in [deduplicator](deduplicator/) service.



