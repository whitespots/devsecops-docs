---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Managing user roles and access control

**Role-Based Access Control (RBAC)** is a powerful security mechanism implemented in the AppSec Portal, ensuring a robust and flexible approach to managing user roles and access privileges. RBAC enables organizations to assign specific roles and permissions to users based on their responsibilities and requirements within the application security ecosystem.

## Roles

A **role** represents a predefined _set of_ [_permissions_](./#permissions) assigned to users. For example, if a user has a role with access to specific products, they can read and edit those product settings (including Auto Validator and Deduplicator rules that affect such products).

<figure><img src="../../../.gitbook/assets/image (127).png" alt="" width="375"><figcaption></figcaption></figure>

To learn how to create and edit users in the Portal, see the [**User management**](user-management.md) page.

### Built-in roles

The AppSec Portal comes equipped with two built-in roles that serve as the foundation for managing user access and permissions:

<table><thead><tr><th width="187">Built-in role</th><th>Permissions</th><th>Notes</th></tr></thead><tbody><tr><td><em><strong>superuser</strong></em></td><td><ul><li>Create, edit, and delete roles and user accounts</li><li>Manage global settings</li><li>Edit product settings</li><li>Manage all product types</li></ul></td><td>Highest-level role, automatically created during the deployment process of the Portal. As the superuser, this role possesses all permissions available within the platform.</td></tr><tr><td><em><strong>default</strong></em></td><td>No permissions</td><td>Built-in role that comes with no permissions assigned. When a user is initially added to the AppSec Portal without any explicitly assigned role, they are automatically assigned the default role. Users with the default role have limited access within the platform. They only can view global settings but cannot modify them.</td></tr></tbody></table>

### Custom roles

While the built-in roles, such as the _superuser_ and _default_ roles, provide a starting point, custom roles enable finer-grained control over user privileges and align access with specific job responsibilities. Here are some reasons why organizations should consider creating custom roles:

1. **Granular access control**: custom roles allow to define precisely which actions and functionalities each user should have access to within the AppSec Portal. By creating roles that align with specific responsibilities, organizations can grant users the appropriate level of access needed to perform their tasks effectively, while preventing unauthorized access to sensitive features or data.
2. **Security and compliance**: custom roles enable organizations to enforce security and compliance measures by limiting access to critical functionality. By assigning permissions based on the principle of least privilege, organizations can mitigate the risk of unauthorized actions, minimize potential vulnerabilities, and adhere to industry-specific regulations or internal security policies.
3. **Workflow optimization**: custom roles can be designed to streamline workflows and promote collaboration. By creating roles that match different job functions, teams can efficiently manage their tasks and focus on their specific responsibilities within the application security process.

For instructions on creating and editing roles in the AppSec Portal, refer to the "**Creating and editing roles**" guide. It provides step-by-step instructions for customizing roles, assigning permissions, and modifying existing roles.

### Multiple role assignment

The Portal supports the assignment of _multiple roles_ to users, offering a flexible and versatile approach to user access and permissions.

Here's how it works in the AppSec Portal:

1. **Unlimited users and roles**: the Portal has no limitations on the number of users that can be added to the system. Organizations can onboard as many users as needed, ensuring that each individual has a dedicated account within the platform. Similarly, there is no restriction on the number of roles that can be created.
2. **Role combinations**: users can be assigned any combination of roles within the Portal. This means that a single user can have multiple roles assigned to them simultaneously.

## Permissions

**Permissions** play a crucial role in determining the actions and functionalities that users can perform within the platform.

<figure><img src="../../../.gitbook/assets/image (87).png" alt=""><figcaption><p>Permissions of the superuser role</p></figcaption></figure>

These permissions can be assigned to roles, allowing to fine-tune user access. Here are the available permissions within the AppSec Portal:

<table><thead><tr><th width="200.66666666666666">Permission</th><th width="445">Description</th></tr></thead><tbody><tr><td><strong>Can manage roles and users</strong></td><td>Users with this permission have administrative privileges over user management within the Portal. They can create custom roles, modify existing roles, create new user accounts, and assign or remove roles for other users (i.e have access to tab "<strong>Users and Roles</strong>").</td></tr><tr><td><strong>Can manage global settings</strong></td><td>Roles with this permission can make changes to configuration options that affect the entire platform, such as global settings ("<a href="../scanner-settings/"><strong>Scanners</strong></a>" and "<a href="../../features/security-metrics/"><strong>Metrics</strong></a>" tab) and integration configurations ("<strong>Integrations</strong>" tab).</td></tr><tr><td><strong>Can edit product settings</strong></td><td>Roles with this permission have the ability to modify the settings of specific products ("<strong>Can manage all product type</strong>", "<strong>Has access to products with types</strong>" and "<strong>Has access to products</strong>" permissions determine which products are available for the role). These <a href="../../features/working-with-products/">settings</a> include configurations such as the product type, Jira project keys, and product-related tags.</td></tr><tr><td><strong>Can manage all product type</strong></td><td>This permission grants the role full control over all product types and their settings providing comprehensive access to manage and configure any product available on the platform.</td></tr><tr><td><strong>Has access to products with types</strong></td><td>This permission allows administrators to specify the product types to which a role has access.</td></tr><tr><td><strong>Has access to products</strong></td><td>Allows administrators to specify individual products to which a role has access.</td></tr></tbody></table>

## RBAC support in Auto Validator and Deduplicator

Role-based permissions enable precise control over user interactions with rules in the [Auto Validator](../../features/auto-validator/) and [Deduplicator](../../features/deduplicator/), ensuring efficient triage and depuplication of vulnerability findings.

<figure><img src="../../../.gitbook/assets/image (98).png" alt=""><figcaption><p>Products affected by the rule example</p></figcaption></figure>

The table below highlights the differences in management and access based on product availability in the AppSec Portal:

<table><thead><tr><th width="185">Permission level</th><th width="129">Role visibility</th><th width="130">Role editing</th><th>Adding/removing affected products from roles</th></tr></thead><tbody><tr><td><strong>No access</strong> (no available product types/products affecting this rule for the role)</td><td>Role is hidden</td><td>N/A</td><td>N/A</td></tr><tr><td><strong>Partial access</strong> (at least one product in this rule is available for the role)</td><td>Role is <mark style="color:green;">viewable</mark></td><td><mark style="color:red;">Restricted</mark></td><td><mark style="color:blue;">Allowed</mark> (only products that are specifically assigned to the role)</td></tr><tr><td><strong>Full access</strong> (all products in a rule are available for the role)</td><td>Role is <mark style="color:green;">viewable</mark></td><td><mark style="color:green;">Allowed</mark></td><td><mark style="color:green;">Allowed</mark></td></tr></tbody></table>
