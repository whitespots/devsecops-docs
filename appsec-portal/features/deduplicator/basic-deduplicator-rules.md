# Basic deduplicator rules

Basic deduplication works during report import, scanner report post-processing and Auditor execution, within the specified scope and using configurable matching criteria.

To set up a rule for Basic Deduplicator, follow the steps below

1. Navigate to **Settings** -> **Maintenance** -> **Basic Dedublication**
2. Select the **Deduplication Criteria**

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

When criteria are chosen, new findings are compared only with those having equal values in selected criteria; otherwise, without selected criteria, new findings are compared with all existing findings in specified scope.

You can select one or more criteria:

* Same branch
* Same Docker Image
* Same Domain
* Same Host
* Same Repository
* Same Cloud account
* Same Scanner
* Same custom field

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

3. Select the **Scope** within which the basic deduplication will take place

* **Product scope**: the results are compared with findings from the specified product to identify possible duplicates. The deduplication process is limited to detections from the specified product only.
* **Product type scope**: new inspection results are compared to the detections of all products with the same product type as the current product. The duplicate search focuses on results from all products with the corresponding product type.
* **Portal scope**: the results are analysed against existing detections in the AppSec Portal to identify duplicates. Results from all products and product types in the system are used to search for duplicates.

<figure><img src="../../../.gitbook/assets/basic dedubl 3.png" alt=""><figcaption></figcaption></figure>
