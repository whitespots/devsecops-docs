---
description: >-
  Get a better understanding of what's really at risk, product by product, with
  the informative Products tab
---

# 📦 Working with products

The **Products** **page** allows you to manage the products in the AppSec Portal. From here, you can create new products, view existing products, and configure the settings for each product.

### Products page

On the Products tab, you can view a list of all products grouped by **product type**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Products can be sorted in _ascending_ and _descending_ order by Name, Risk, Triaged and Resolved status using the **Sort** button.

<figure><img src="../../../.gitbook/assets/image (149).png" alt=""><figcaption></figcaption></figure>

**Filter** by product type and tags provides an easy way to navigate between different product types and/or product tags, default product.

<figure><img src="../../../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

### Product Dashboard

Clicking on a product will take you to the product dashboard

This dashboard provides an overview of the product's risk profile, including the **Product Weighted Risk Trend** and a **Risk Appetite** graph showing the current state of the security posture for this specific product.

<figure><img src="../../../.gitbook/assets/image (151).png" alt=""><figcaption></figcaption></figure>

The dashboard also displays **statistics** on unverified, verified, and resolved findings, as well as a **list of all findings** grouped by verification status. Any finding in the list **can be expanded** to show all of its information.



<table data-card-size="large" data-view="cards" data-full-width="true"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td></td><td></td><td><a href="../../../.gitbook/assets/prod 4.png">prod 4.png</a></td></tr><tr><td></td><td></td><td></td><td><a href="../../../.gitbook/assets/prod5.png">prod5.png</a></td></tr></tbody></table>

#### **Business Criticality**

[_Fill survey_](risk-assessment.md) for every product to designate overall **business criticality** or set it _manually_:

<figure><img src="../../../.gitbook/assets/bus crit.gif" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The **default** value for business criticality is **10**. Unless you set a different value, any product is considered to be _<mark style="color:red;">highly critical</mark>_. Please adjust criticality level so that your metrics reflect a more realistic [_risk trend_](https://docs.whitespots.io/appsec-portal/features/security-metrics/wrt-weighted-risk-trend).
{% endhint %}
