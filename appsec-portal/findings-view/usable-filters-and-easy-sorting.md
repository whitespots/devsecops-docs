# Usable filters and easy sorting

**AppSec Portal** provides **all kinds of filters** to handle large numbers of reports:

<figure><img src="../../.gitbook/assets/Video_2024_08_01-1(1).gif" alt=""><figcaption></figcaption></figure>

You can filter your findings not only by **date of creation**, but also by **verification date**, **assignment date** and **resolving date**:

<figure><img src="../../.gitbook/assets/image (165).png" alt=""><figcaption></figcaption></figure>

You can **select several filters** at once for sampling accuracy:

<details>

<summary>SLA Violated - include or exclude:</summary>

* [x] Any
* [x] Verification SLA Violated
* [x] Assign SLA Violated
* [x] Resolve SLA Violated

</details>

<details>

<summary>Severity</summary>

* [x] Critical
* [x] High
* [x] Medium
* [x] Low
* [x] Info

</details>

<details>

<summary>Tags</summary>

* [x] Tags - select from drop-down list
* [x] Match Tags: Any, At least or Strict&#x20;
* [x] Not Tags - select from drop-down list

</details>

<details>

<summary>Found by: include or exclude</summary>

* [x] Select **scanner name** from drop-down list of scanners (multi select option)

</details>

<details>

<summary>File path</summary>

* [x] Enter file path

</details>

<details>

<summary>Branch</summary>

* [x] Conteins: enter branch name
* [x] All
* [x] Empty
* [x] Not empty

</details>

<details>

<summary>Dependency</summary>

* [x] Enter dependency

</details>

<details>

<summary>Vulnerable URL</summary>

* [x] Enter vulnerable URL

</details>

<details>

<summary>Finding source</summary>

* [x] All
* [x] Portal
* [x] Other

</details>

<details>

<summary>Assets</summary>

* [x] Repository SSH URL: enter URL
* [x] Docker Image: enter registry
* [x] Domain: enter domain
* [x] Host: enter host
* [x] Cloud account: enter cloud account name
* [x] Asset tags: select tags from dropdown list

</details>

<details>

<summary>Automation</summary>

* [x] Any
* [x] Auto resolved by scanner setting
* [x] Auto verified by rule
* [x] Auto rejected by rule
* [x] Affected by CVSS rule
* [x] Affected by Autovalidator rule
* [x] Imported in Audit

</details>

<details>

<summary>Group</summary>

* [x] Select a group name from the drop-down list to be displayed as a result of filtering (multi-select option)

</details>

<details>

<summary>CWE </summary>

* [x] Select CWE from the drop-down list (multi-select option) - include or exclude
* [x] All&#x20;
* [x] Empty&#x20;
* [x] Not empty

</details>

<details>

<summary>Product</summary>

* [x] Product: select a product from the drop-down list to be **displayed** as a result of filtering (multi-select option)
* [x] Not product: select a product from the drop-down list to **exclude** from the filter result  (multi-select option)
* [x] Product type: select a product type from the drop-down list to be displayed as a result of filtering (multi-select option)
* [x] Product tags: select a product tags from the drop-down list to be displayed as a result of filtering (multi-select option)
* [x] Product Business Criticality: select a filter range from 1 to 10

</details>

You can also **sort** the list of findings in ascending or descending order by clicking on the column header:

<figure><img src="../../.gitbook/assets/sort.gif" alt=""><figcaption></figcaption></figure>

Click on the loupe sign to **search by specific name** (in finding name, in description or in tag):

<figure><img src="../../.gitbook/assets/found by name.gif" alt=""><figcaption></figcaption></figure>
