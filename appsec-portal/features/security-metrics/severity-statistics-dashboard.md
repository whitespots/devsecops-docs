# Severity Statistics Dashboard

* [**Current Weighted Risk Trend**](severity-statistics-dashboard.md#current-weighted-risk-trend)
* [**Mean Time of Status Change**](severity-statistics-dashboard.md#mean-time-of-status-change)
* [**Findings count**](severity-statistics-dashboard.md#findings-count)

&#x20;**Severity Statistic view:**

<figure><img src="../../../.gitbook/assets/dash2.png" alt=""><figcaption></figcaption></figure>

You can **customise your dashboard** based on your needs by clicking the **Metrics button** <img src="../../../.gitbook/assets/image (1) (1) (1) (1).png" alt="" data-size="line">  on the right panel:

<figure><img src="../../../.gitbook/assets/cust metrics.gif" alt=""><figcaption></figcaption></figure>

The timeline of the charts can be customized to show data for the last 3 days, last week, last month, or last year, providing flexibility in analyzing different time ranges.&#x20;

<figure><img src="../../../.gitbook/assets/period.png" alt=""><figcaption></figcaption></figure>

**Select the products** for which you want to see data on the chart by selecting them from the _Products to Select_ section. You can search, filter (by product type, included or excluded tag) and include or exclude selected products from the data display by moving the _Exclude Selection_ slider.

<figure><img src="../../../.gitbook/assets/prod dashboard.png" alt=""><figcaption></figcaption></figure>

### Current Weighted Risk Trend

[**Weighted Risk Trend (WRT)**](wrt-weighted-risk-trend.md) metric empowers organizations to measure and track the state of security in a business-oriented manner. The **General WRT** is calculated by combining the WRT of each product, taking into account their respective severity weights, findings count, and business criticality assessments.

<figure><img src="../../../.gitbook/assets/weight risk trend.png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Note that the **General Weighted Risk Trend** displays the [WRT](wrt-weighted-risk-trend.md), risk appetite and severity weight values. Be sure to [set the appropriate weights](https://docs.whitespots.io/appsec-portal/features/security-metrics/metrics-settings) before viewing the graph. Otherwise, the graph may be distorted by incorrect weight values.
{% endhint %}

By regulary tracking the following global metrics, you can gain a better understanding of your security posture and make informed decisions to enhance your overall security strategy.

### Mean Time of Status Change

By monitoring the **Status change mean time** graph in relation to the [**SLA**](metrics-settings/sla.md) requirements, you can effectively manage and prioritize your remediation efforts, ensuring that critical vulnerabilities are promptly addressed and mitigated according to the established timelines.

Customise the view of the metric view using the Findings Status Change Time Statistics section of the Metrics Settings.

<figure><img src="../../../.gitbook/assets/status change.png" alt=""><figcaption></figcaption></figure>

*   **Average Vulnerability Age** (**AVA**) calculates the average age of vulnerabilities from _creation_ to _remediation_. It helps to determine how long vulnerabilities pose a potential risk.

    <figure><img src="../../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/mean time of status change.png" alt=""><figcaption><p>AVA graph</p></figcaption></figure>

*   **Mean Time to Detection** (**MTTD**) measures the average time it takes to _verify_ vulnerabilities from the moment they are _created_ . A shorter MTTD indicates an effective and timely vulnerability detection process.

    <figure><img src="../../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (144).png" alt=""><figcaption><p>MTTD graph</p></figcaption></figure>

*   **Mean Time to Rejection** (**MTR**) measures the average time it takes for a finding to be _rejected_ after _creation_. It provides insights into the speed of handling findings that are determined to be false positives.

    <figure><img src="../../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/mean time 2.png" alt=""><figcaption><p>MTR graph</p></figcaption></figure>

*   **Mean Time to Remediation** (**MTTR**) calculates the average time it takes to _remediate_ vulnerabilities from the moment they are _verified_. A shorter MTTR indicates an efficient vulnerability resolution process.

    <figure><img src="../../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (145).png" alt=""><figcaption><p>MTTR graph</p></figcaption></figure>

*   **Mean Time to Product Task Assignment** (**MTTAp**) measures the average time it takes for a _validated_ finding to be assigned to a developer (_assignee_) in the Jira product space from the time it is validated. It helps to track the speed at which results are processed after validation and the initiation of the fixing process.&#x20;

    <figure><img src="../../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (146).png" alt=""><figcaption><p>MTTAp graph</p></figcaption></figure>

**Mean Time to Security Task Assignment** (**MTTAs**) measures the average time it takes for a _validated_ finding to be assigned to a developer (_assignee_) in the Jira security space from the time it is validated. It helps to track the speed at which results are processed after validation and the initiation of the fixing process.&#x20;

<figure><img src="../../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (147).png" alt=""><figcaption><p>MTTAs graph</p></figcaption></figure>

### Findings count

<figure><img src="../../../.gitbook/assets/count.png" alt=""><figcaption></figcaption></figure>

Customise the view of the metric view using the Findings Count Statistics section of the Metrics Settings.

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

1. **Finding Discovery Rate** (**FDR**) measures the rate at which new vulnerabilities are _verified per day_, either manually or automatically (through the Auto[ Validator](../../auto-validator/)). It helps you evaluate the effectiveness of your Auto Validator's rules and security team.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption><p>FDR chart</p></figcaption></figure>

2. **False Positive Rate** (**FPR**) quantifies the rate of reported vulnerabilities that are later determined to be _false positives per day_ manually or by [Auto Validator](../../auto-validator/). A lower false positive rate indicates the accuracy of your vulnerability detection tools and methodologies.

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption><p>FPR chart</p></figcaption></figure>

3. **Vulnerability Remediation Rate** (**VRR**) tracks the rate at which vulnerabilities are _resolved per day_, either manually or automatically (through the [Auto Closer](../../general-portal-settings/scanner-settings/#auto-closer)). This metric evaluates the efficiency of your vulnerability resolution process.

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption><p>VRR chart</p></figcaption></figure>
