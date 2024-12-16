# 🗒️ Release notes

**release\_v24.12.1 (latest)**

```
- Сustom importers
- GIT integrations healthcheck and error log
- Autovalidator, Deduplicator, CVSS launch frequency in seconds
- Improved metrics caching
- Minor UI and bug fixes
```

**release\_v24.11.3**

```
- Added tags to scanners
- Automation rules execution order:
1. reject
2. risk accept
3. confirm

- Assets and tags as parameters for automation rules
- Skip ssl verification flag for a message broker
- Various importers bug fixes
```

**release\_v24.11.2**

```
- New asset creation logic on import. 
Now you can only add an asset with a scanner report and it will be added 
to the default product or not added if the asset already exists in one 
of the existing products. 
So, no need to use products for all our CI users. 
Those who use auditor - you are great, it's nothing to worry about 😄

- Bulk audits run
- Customizable UI tables. Now you can pick up your favourite columns and sort data by them
```

**release\_v24.11.1**&#x20;

```
- Multiple git instances
- Portal internal and external host urls
- Misconfigurations case in trivy importer
- Various bug fixes
```

**release\_v24.10.2**

* New token-based authorization for Jira <mark style="color:green;">**`NEW`**</mark>
* Job sequence per asset <mark style="color:green;">**`NEW`**</mark>
* Reworked version control comments mode settings <mark style="color:blue;">**`UPDATE`**</mark>
* New auditor job settings <mark style="color:green;">**`NEW`**</mark>
* Minor bugfixes <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.10.1**&#x20;

1. Improved version control systems integration: delayed comments, deletion of previous comments, including findings from other branches in pull requests <mark style="color:blue;">**`UPDATE`**</mark>
2. Some notifications now include user information <mark style="color:blue;">**`UPDATE`**</mark>
3. Small fixes in importers <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.09.1**&#x20;

1. Webhook based integration with GitHub and GitLab: push events trigger scans, merge requests trigger comments <mark style="color:green;">**`NEW`**</mark>
2. Reworked Assets table in product <mark style="color:blue;">**`UPDATE`**</mark>
3. Added configuration of default job sequence <mark style="color:green;">**`NEW`**</mark>
4. Improved Job list in Auditor settings <mark style="color:blue;">**`UPDATE`**</mark>
5. Minor UI bug fixes <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.08.4**

1. **Date Selection for Temporarily Accepted Findings**: Introduced a date select feature for temporarily accepted findings, allowing users to specify a review date. <mark style="color:green;">**`NEW`**</mark>
2. **Russian Portal Translation**: The portal is now available in Russian. <mark style="color:green;">**`NEW`**</mark>
3. **Added Assets to Jira Issue Description**s: Improved Jira integration by automatically including relevant assets in the issue description. <mark style="color:green;">**`NEW`**</mark>
4. **Improved Swagger**: Updated and improved Swagger documentation, making it easier for developers to understand and use the API. <mark style="color:blue;">**`UPDATE`**</mark>
5. **Bugfix**: Products were not visible on validation rule creation screen <mark style="color:blue;">**`UPDATE`**</mark>
6. **Bugfix**: Filtering by tags resulted in duplicate products <mark style="color:blue;">**`UPDATE`**</mark>
7. **Bugfix**: Wrong triage status after re-verifying a result <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.08.3**

1. **Status event notifications**: Now include findings IDs <mark style="color:green;">**`NEW`**</mark>
2. **CWE Filter**: Displays total number of findings per CWE <mark style="color:green;">**`NEW`**</mark>
3. **Added Days Accepted for Temporary Risk Accepted Findings** <mark style="color:green;">**`NEW`**</mark>
4. **Added asset creation for the Asset Audit endpoint**: The Assets Audit Endpoint has been enhanced with the ability to create assets, streamlining asset management within the audit process. <mark style="color:green;">**`NEW`**</mark>
5. **Notifications**: Now use application/json content type <mark style="color:green;">**`NEW`**</mark>
6. **Select different triage statuses for top CWE recommendations** <mark style="color:green;">**`NEW`**</mark>
7. **Added integrations to Patch Request for Findings endpoint&#x20;**<mark style="color:green;">**`NEW`**</mark>

**release\_v24.08.2**&#x20;

1. **Custom field for findings and basic deduplication**: Introduced the ability to add custom fields to findings, along with basic deduplication functionality. <mark style="color:green;">**`NEW`**</mark>
2. **SSL configuration for notifications**: Added SSL configuration options for notifications, improving the security and reliability of notification delivery. <mark style="color:blue;">**`UPDATE`**</mark>
3. **Minor bug fixes**: Various minor issues have been addressed to improve system stability and performance. <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.08.1**&#x20;

1. **New statuses**: Introduced new statuses (_Temporarily Risk Accepted_, _Permanently Risk Accepted_) to better categorise and manage risk acceptance in findings. <mark style="color:green;">**`NEW`**</mark>
2. **Autovalidator actions for new findings statuses**: Added autovalidator actions to handle the newly introduced issue statuses. <mark style="color:green;">**`NEW`**</mark>
3. **Jira Issue Status Mappings for New Issue Statuses**: Implemented mappings for Jira issue statuses to reflect the new issue statuses. <mark style="color:green;">**`NEW`**</mark>
4. **Configurable Two-Way Binding for Jira Issue Statuses**: Enabled configurable two-way binding for Jira issue statuses. <mark style="color:green;">**`NEW`**</mark>
5. **Status change event added for notifications**: Added a status change event to trigger notifications to keep users informed of any changes to issue statuses. <mark style="color:green;">**`NEW`**</mark>
6. **Enhanced findings automation filters**: Improved findings automation filters. <mark style="color:blue;">**`UPDATE`**</mark>
7. **Minor bug fixes**: Various minor bugs have been addressed to improve overall system performance and reliability. <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.07.3**&#x20;

1. **Added support for Common Weakness Enumeration (CWE)**: Allows users to focus on the most common security issues. <mark style="color:green;">**`NEW`**</mark>
2. **Refactored importers to support CWE**: Importers have been refactored to include CWE support, allowing for more comprehensive and detailed analysis of security issues. <mark style="color:green;">**`NEW`**</mark>
3. **Added preview of assets and products for selected findings**: Added the ability to preview assets and products associated with selected findings, providing a clearer understanding of the impact and context of each issue. <mark style="color:green;">**`NEW`**</mark>
4. **Organisation removed from repository URL configuration**: Simplified repository URL configuration by removing the organisation parameter. The portal can now automatically retrieve most information from the repository asset, streamlining setup and configuration. <mark style="color:blue;">**`UPDATE`**</mark>
5. **Minor bug fixes:** Various minor bugs have been addressed to improve overall system performance and reliability. <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.07.2**

1. **UI improvements**: Made several improvements to the user interface for a more intuitive and user-friendly experience. <mark style="color:blue;">**`UPDATE`**</mark>
2. **Jira Webhooks Improvements**: Improved integration with Jira webhooks for more reliable and efficient issue tracking and management. <mark style="color:blue;">**`UPDATE`**</mark>
3. **CVSS Rules in Admin Interface**: Added the ability to manage Common Vulnerability Scoring System (CVSS) rules directly in the admin interface for easier configuration and updates. <mark style="color:green;">**`NEW`**</mark>
4. **Stability improvements**: Audit schedules are now more stable <mark style="color:blue;">**`UPDATE`**</mark>
5. **Bug fixes**: Various minor bugs have been addressed to improve overall system performance and reliability.  <mark style="color:blue;">**`UPDATE`**</mark>
6. **Maintenance Some microservices removed**: Some microservices have been removed from the system. <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.07.1**&#x20;

1. **Grouping feature for Auto Validator**: A new grouping feature has been added to the Auto Validator, allowing users to organise and categorise validation results more efficiently. <mark style="color:green;">**`NEW`**</mark>
2. Minor bugfixes <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.06.3.1**

1. Minor bugfixes <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.06.3 &#x20;

1. **Select Items Using Shift Key**: Added the ability to select multiple items using the Shift key. <mark style="color:green;">**`NEW`**</mark>
2. **Nessus Importer**: Introduced a new Nessus importer feature, enabling seamless integration with Nessus for importing and managing vulnerability data. <mark style="color:green;">**`NEW`**</mark>
3. **UI Improvements**: Made several enhancements to the user interface for a more intuitive and user-friendly experience. <mark style="color:blue;">**`UPDATE`**</mark>
4. **Minor Fixes**: Addressed various minor bugs to improve system performance and reliability. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.06.2&#x20;

1. **Bulk Audits for Assets:** Introduced the ability to perform bulk audits on assets, allowing users to efficiently manage and review multiple assets simultaneously. <mark style="color:green;">**`NEW`**</mark>
2. **Linear Regression Based Suggestions:** Implemented linear regression analysis to provide intelligent suggestions and predictions. <mark style="color:green;">**`NEW`**</mark>
3. **Improved Stability:** Made several under-the-hood improvements to enhance the overall stability of the system. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.06.1&#x20;

1. **Monthly risk trend line**: Introduced a monthly risk trend line to help track and visualise risk changes over time. <mark style="color:green;">**`NEW`**</mark>
2. **Recommendations**: Added a recommendation feature to provide actionable insights and suggestions for risk mitigation. <mark style="color:green;">**`NEW`**</mark>
3. **Importers for Hadolint and Dependency Track**: New importers have been added to support Hadolint and Dependency-Track, enabling seamless integration and data import. <mark style="color:green;">**`NEW`**</mark>
4. **Filters for findings**: Implemented filters for findings by product and asset tags, making it easier to narrow and focus on specific areas of interest. <mark style="color:green;">**`NEW`**</mark>

#### release\_v24.05.1 &#x20;

1. **New/Fixed Counters per Asset and Scanner**: The audit view now includes updated counters for each asset and scanner, providing more accurate and detailed insights. <mark style="color:blue;">**`UPDATE`**</mark>
2. **Customizable Dashboard Metrics**: Easily customize your dashboard with metrics for different products, product types, products with tags, and more. <mark style="color:green;">**`NEW`**</mark>
3. **New Dashboard:** Introducing a new dashboard for better user experience and enhanced data visualization. <mark style="color:blue;">**`UPDATE`**</mark>
4. **Cloud Account as an Asset Type**: Now supports cloud accounts (AWS, GCP, Azure) as asset types. Scanning these accounts is now straightforward and well-documented. <mark style="color:green;">**`NEW`**</mark>
5. **Asset Transfer Between Products**: You can now transfer assets between products along with their findings. This means that if you change the product, all issues will remain consistent per repository, domain, host, and cloud account. <mark style="color:green;">**`NEW`**</mark>

#### release\_v24.04.1 &#x20;

1. **New Screen for Assets**: Added a new screen to manage assets more effectively.  <mark style="color:green;">**`NEW`**</mark>
2. **Even More Stability**: Implemented further improvements to enhance the stability of the system. <mark style="color:blue;">**`UPDATE`**</mark>
3. **Minor Bug Fixes**: Addressed various minor bugs and issues. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.03.3&#x20;

1. **Groups functionality** : You can now create your own groups and filter your findings by these groups <mark style="color:green;">**`NEW`**</mark>
2. **Jira issues to reports**: Reports now include issue information from Jira <mark style="color:green;">**`NEW`**</mark>
3. **PHPCodeSniffer importer**: An importer for PHPCodeSniffer has been added <mark style="color:green;">**`NEW`**</mark>
4. **Improved automation processes&#x20;**<mark style="color:blue;">**`UPDATE`**</mark>
5. **Copy button for Auditor jobs**: Added Copy button for Auditor jobs <mark style="color:green;">**`NEW`**</mark>
6. **Tag management screen**: Added tag management screen <mark style="color:green;">**`NEW`**</mark>

#### release\_v24.03.2 &#x20;

1. **Backend performance**: Enhanced backend performance for a faster system operation. <mark style="color:blue;">**`UPDATE`**</mark>
2. **Concurrency setting for db\_helper**: Added concurrency settings for the db\_helper to optimise database queries when dealing with large datasets or concurrent requests. <mark style="color:green;">**`NEW`**</mark>

#### release\_v24.03.1&#x20;

1. **Advanced filtering options**: Users can now filter finds using the new Automation parameter, which includes auto-resolve by scanner settings, auto-verify and auto-reject by rule,  affected by CVSS rule. This allows you to monitor and analyse your discoveries in more detail. <mark style="color:green;">**`NEW`**</mark>
2. **Jira due date**: Added support for setting Jira due date, providing more flexibility in task management. <mark style="color:green;">**`NEW`**</mark>
3. **Bugfix and performance improvement**: Addressed issues related to load handling, ensuring smoother performance under varying workloads. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.02.3&#x20;

1. **Notifications Webhook Feature**: Get notified about results that match specific filters. <mark style="color:green;">**`NEW`**</mark>
2. **Role search**: Search role with the addition of search by title functionality. <mark style="color:green;">**`NEW`**</mark>
3. **Improved CVSS 3.1 integration**: We've updated our scoring system to use environment scores instead of base scores for CVSS 3.1. <mark style="color:green;">**`NEW`**</mark>
4. **Bug Squashing**:We've addressed several minor bugs to ensure a smoother user experience. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.02.2 &#x20;

1. **Automatic Product Selection**: Simplify scheduling by letting **tags** do the work for you. <mark style="color:green;">**`NEW`**</mark>
2. **Jira Components**: Integrate seamlessly with Jira for better project management. <mark style="color:green;">**`NEW`**</mark>
3. **Bulk Jira Issues Link**: Save time by linking multiple Jira issues at once. <mark style="color:green;">**`NEW`**</mark>

#### release\_v24.02.1&#x20;

1. **CVSS**: We've added support for Common Vulnerability Scoring System (CVSS) to provide more comprehensive vulnerability assessment. Now, you can better understand the severity of vulnerabilities and prioritize your remediation efforts effectively. <mark style="color:green;">**`NEW`**</mark>
2. **Product Business Criticality Filter**: Introducing a new filter option that allows you to streamline your findings based on product business criticality. Easily identify and focus on vulnerabilities impacting your most crucial business assets, enabling you to mitigate risks efficiently. <mark style="color:blue;">**`UPDATE`**</mark>
3. **Bug Fixes**: We've squashed some minor bugs to ensure smoother functionality and a more seamless user experience. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.01.1.1&#x20;

1. **Bug Fixes and Hotfixes**: This release includes updates addressing various bugs and implementing necessary hotfixes to enhance the overall stability and performance of the system. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.01.1&#x20;

1. **SSO Roles Mapping**: Easily configure Single Sign-On (SSO) roles mapping for seamless role alignment with external identity providers <mark style="color:green;">**`NEW`**</mark>
2. **Django Admin Panel Access**: Grant customized access to the Django admin panel for specified users, enhancing administrative control <mark style="color:green;">**`NEW`**</mark>
3. **Product Filter Enhancement**: Improved usability with an updated interface for product filters<mark style="color:blue;">**`UPDATE`**</mark>
4. **Multiple Subgroups Support in Repositories**: Now supports multiple subgroups within repositories for a more comprehensive organizational structure<mark style="color:blue;">**`UPDATE`**</mark>
5. **Customizable Basic Deduplication Criteria:** Introducing the ability to customize basic deduplication criteria for more precise and tailored results <mark style="color:green;">**`NEW`**</mark>
6. **Preservation of Dot Symbol in filepath**: Dot symbols at the beginning of filepaths are now preserved, maintaining file reference integrity<mark style="color:blue;">**`UPDATE`**</mark>
7. **UI Flag for Archived Repositories**: Added a new UI flag to indicate archived repositories on the import screen, streamlining repository management. <mark style="color:green;">**`NEW`**</mark>

#### release\_v23.12.4&#x20;

1. Load optimization
2. Added reject status for jira
3. Deduplicator fixed for assets
4. Reworked product filter by tags

#### release\_v23.12.3&#x20;

1. Added affected products for repo url configs
2. Added token auth for endpoints
3. Added loading repos from gitlab and github

#### release\_v23.12.2

1. Repository link logic optimization
2. UI improvements (for assets in general)
3. New finding fields (repository, docker image, domain, host)
4. Assets are passed to report generator

#### release\_v23.12.1&#x20;

1. Reworked assets and git repo url

#### release\_v23.11.1

1. Auditor integrations
2. Findings file path fixed
3. Assign tags fixed
4. Added finding filters by product and product type

#### release\_v23.10.1

1. Added new fields for sso configurations
2. Improved sso error handling
3. Reworked bulk actions
4. Added branch for findings
5. Added downloading risk overview in .csv
6. Importer fix

#### release\_v23.09.2&#x20;

1. Added SSO integrations
2. Added prowler importer
3. Minor bug fixes

#### release\_v23.09.1&#x20;

1. Added report generation

#### release\_v23.08.3

1. Added global rules for Auto Validator and Deduplicator
2.  Added new scanners: \
    \- GitLab Gemnasium \
    \- GitLab KICS - GitLab Gitleaks \
    \- GitLab OWASP Zap

    \- GitLab Bandit \
    \- GitLab ESLint \
    \- GitLab Semgrep

#### release\_v23.08.2&#x20;

1. Added possibility to specify jira issue types
2. Added jira priority-severity mapping
3. Added jira status mapping
4. Added possibility to reopen a resolved finding

#### release\_v23.08.1&#x20;

1. Added new functionality to the scanner settings: Findings Grouping
2. Fixed incorrect work of basic deduplicator and autocloser with dependency and url fields

#### release\_v23.07.2

1. Resolved an issue where products were being erroneously created with default settings in the common product type, even when the user lacked access to this specific product type.
2. Addressed the problem with case-sensitive fields in severity mapping.&#x20;
3. jwt token expiration date moved from the body to cookies.
4. Added slicing to metrics.

#### release\_v23.07.1

Resolved the issue causing a bug related to product deletion&#x20;

#### release\_v23.06.2

1. RBAC Support:
   * Role-Based Access Control (RBAC) is now supported, providing improved user management and access control.
   * A new "Users and Roles" tab has been added, allowing easy management of users and roles within the portal.
2. Affected Products field in Auto Validator and Deduplicator rules:
   * Auto Validator and Deduplicator rules now include an "Affected Products" field.
   * Users can associate specific products with rules, granting greater flexibility and customization.
   * Role-based permissions control user interactions with rules based on product availability:
     * Rule are hidden, if it has no available products for the user.
     * Rule are viewable and product association management allowed if at least one product in this rule is available for the user, but rule editing is restricted.
     * Full control granted if all products in a rule are available for the user.
3. Tag support for products:
   * Tags can now be added to products from the product's "Options" page, allowing for better organization and categorization of application assets.
4. New filters on "Product" page:
   * Two new filters, "Tags" and "Not tags," have been introduced on the "Product" page.  These filters enable easy searching and filtering of products based on assigned tags, streamlining navigation and management.
5. AWS Security Hub importer:
   * We are excited to introduce the new **AWS Security Hub importer**, seamlessly integrating your AWS security ecosystem with the AppSec Portal.
   * Import security findings from AWS Security Hub directly into the portal, enhancing your vulnerability management process.
6. Enhanced SLA violation filtering:
   * The "SLA Violated" filter has been enhanced to allow filtering findings based on the type of SLA violation.
   * You can now filter findings by Verification SLA violated, Assign SLA violated, or Resolve SLA violated.
7. Auto Validator and Deduplicator enhancements:
   * The Auto Validator rules now supports searching findings based on specified values in the Vulnerable URL, Dependency fields and by Import Source (internal or external at your option).
   * Deduplicator rules have been enhanced with new criteria to determine the equality of original and duplicate findings — "Same dependency" and "Same vulnerable URL".
   * Additionally, Deduplicator rules now offer the ability to search findings for specified values in the Vulnerable URL, Dependency fields, and by Import Source, with the option to choose internal or external finding’s sources.

#### release\_v23.06.1

* Added symkey deletion via
* Changed entrypoint number of threads

#### release\_v23.05.3

* Resolved the issue causing a bug related to product deletion&#x20;

#### release\_v23.05.2

* Metrics added
* Added possibility to add scanner reports via UI
* Nuclei importer updated
* The maximum allowable length for the description in a search result has been increased to 3000 characters.

#### Realease\_v23.05.1

* Introducing the new "Scanners" page with enhanced functionality:
  * Added settings for each scanner:
    * including the auto-closer feature for previously identified findings that are not present in new scanner reports.
    * implemented a custom Jira description feature for more readable scanner descriptions.
    * Introduced a custom severity mapping feature for mapping severity types specific to each scanner.
* Additionally, the following new features have been implemented:
  * "Finding" view now includes the ability to insert and delete images in findings, which can be exported to corresponding Jira tasks.
* New product settings features:
  * Added ability to set product-related tags and push those tags to the corresponding Jira tasks.
  * Added a toggle button to push the product title to Jira task labels.
* Other changes and improvements include:
  * Added a health check for the back container.
  * Transitioned from using fixtures to migrations.
  * Implemented various minor bug fixes.

#### release\_v23.04.5

* Implemented minor bug fixes to address various issues.

#### release\_v23.04.4

* Deployed a hotfix to resolve the Jira authentication issue within the product WRT (Web-based Reporting Tool).

#### release\_v23.04.3

* Added WRT history for every product with updates every 24 hours.
* Bug hotfixes and minor improvements.
* Added toggle button "delete tasks for rejected findings" in Jira integration page.
