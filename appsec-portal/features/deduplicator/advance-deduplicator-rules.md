---
description: To set up a rule for Deduplicator, follow the steps below
---

# Advance Deduplicator rules

1. Select the **Deduplicator**, followed by clicking on the **Rule** button

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

1. Define the products to which the rule will apply or leave All as default

<figure><img src="../../../.gitbook/assets/dedublic rule 1.png" alt=""><figcaption></figcaption></figure>

3. Select one or more **identity criteria** of original and duplicate findings_:_

* **same product**
* **same title**
* **same file path**
* **same line number**
* **same dependency**
* **same vulnerable URL**&#x20;

<figure><img src="../../../.gitbook/assets/dedubl rule 2.png" alt=""><figcaption></figcaption></figure>

4. Create indications for findings designated for the **original scope** within the Original section:

Select a **parameter** and specify its **value** (presence or absence of a value) to be used in the running of the deduplication rules.\
Available parameters:

* **title**
* **description**
* **file path**
* **branch**
* **scanner**
* **dependency**
* **vulnerable url**
* &#x20;**import source** (internal or external at your option)

You can combine terms via join, just click on the plus button

<figure><img src="../../../.gitbook/assets/dedubl rule3.png" alt=""><figcaption></figcaption></figure>

5. Create indications for findings designated for the **dublicate scope** within the Dublicate section. These conditions must be defined with the **same parameters** as for the original scope, but with **other values**

<figure><img src="../../../.gitbook/assets/dedublic rule 4.png" alt=""><figcaption></figcaption></figure>

6. Click the **Active** slider to activate the rule
7. Click the **Submit** button to apply the deduplication rule to your scan results

<figure><img src="../../../.gitbook/assets/dedubl rule 6.png" alt=""><figcaption></figcaption></figure>

Deduplicator will **automatically** identify and remove any duplicate findings based on the rule you have created

<figure><img src="../../../.gitbook/assets/dedubl 5.png" alt=""><figcaption></figcaption></figure>
