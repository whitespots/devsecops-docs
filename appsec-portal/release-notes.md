# 🗒️ Release notes

#### release\_v24.04.1  (latest)

1. **New Screen for Assets**: Added a new screen to manage assets more effectively.  <mark style="color:green;">**`NEW`**</mark>
2. **Even More Stability**: Implemented further improvements to enhance the stability of the system. <mark style="color:blue;">**`UPDATE`**</mark>
3. **Minor Bug Fixes**: Addressed various minor bugs and issues. <mark style="color:blue;">**`UPDATE`**</mark>

#### release\_v24.03.3&#x20;

1. **Groups functionality** : You can now create your own groups and filter your findings by these groups <mark style="color:green;">**`NEW`**</mark>
2. **Jira issues to reports**: Reports now include issue information from Jira <mark style="color:green;">**`NEW`**</mark>
3. **PHPCodeSniffer importer**: An importer for PHPCodeSniffer has been added <mark style="color:green;">**`NEW`**</mark>
4. **Improved automation processes **<mark style="color:blue;">**`UPDATE`**</mark>
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
