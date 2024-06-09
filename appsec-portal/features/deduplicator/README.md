---
description: >-
  Deduplicator can help streamline the vulnerability management process and save
  time by identifying and removing duplicate findings
---

# Deduplicator

## What is deduplication

**Deduplication** is the process of _identifying_ and _removing duplicate_ findings from multiple scanners. \
If an organization uses _**multiple scanners**_ to test its software applications, the same vulnerabilities may be found by different scanners. In such cases, deduplication helps to identify the original findings and remove duplicates, thus streamlining the vulnerability management process.

AppSec Portal offers two types of deduplication: **Basic** and **Advanced**.

## How Deduplication works in AppSec Portal

### **Basic Deduplication:**&#x20;

Upon receiving a new finding, the basic deduplication process checks for duplicates within the selected scope before adding it in the database. The scope can be [defined ](basic-deduplicator-rules.md)by the Product, Product type, or Portal scope. Parameters such as Branch, Docker image, Domain, Host, Repository, and Scanner are considered. If a duplicate is found, the new finding is ignored and not added to the database.

### Advanced Dedublicator:

Advanced Deduplication in AppSec Portal goes beyond the basic identification of duplicates by searching within previously identified findings recorded in the database. This process ensures a comprehensive approach to eliminating redundancy in vulnerability management.

When the advanced deduplication process is initiated, the system searches for matches among the findings already stored in the database.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

AppSec Portal's **Deduplicator** feature allows to set up deduplication rules based on specific _criteria_ and _instructions_.

After configuring the deduplication rules, you'll obtain **two sets** of findings: the originals and the duplicates. The originals encompass the findings deemed within the original scope, whereas the duplicates consist of findings that are replicated across various scanners (**collection of sets**)

AppSec Portal then analyzes the duplicate findings in accordance with the [specified configurations](basic-deduplicator-rules.md), comparing them with the original findings. If any finding within the duplicate scope matches a finding in the original scope based on the specified settings, that particular finding will be removed from the database.

{% hint style="info" %}
Please note that the Deduplicator feature is limited to a basic deduplication in the free license, it works at the stage of importing findings into the database, removing full duplicates. If you wish to use **custom rules**, you will need to **upgrade to a paid license**.
{% endhint %}
