# WRT (Weighted Risk Trend)

Our team decided to adopt best practices and draw inspiration from [HP's ideas](https://owasp.org/www-pdf-archive/Magic\_Numbers\_-\_5\_KPIs\_for\_Measuring\_WebAppSec\_Program\_Success\_v3.2.pdf), which led us to discover overlaps with the widely used _error budget_ practice. We believe that utilizing the WRT metric would be a suitable solution to enhance security operations.

**Weighted Risk Trend** (WRT) is one of a **Key Performance Indicators** (KPIs) and provides **business-level context** to security-generated data.

**WRT metric** is a measure that expresses the state of security in numerical terms, without diving into technical details. The metric is linked to **business criticality**, which is linked to the risks associated with the vulnerabilities that exploit them. WRT can provide business value by helping teams identify and address security risks.

WRT is calculated using the formula:

<figure><img src="../../../.gitbook/assets/image (129).png" alt=""><figcaption></figcaption></figure>

* each type of **multiplier** is equal to the corresponding severity weight;
* **defects** is equal to the number of findings of this severity type;
* **business criticality** — an assessment of the importance of the product to the company, ranging from one to ten.
