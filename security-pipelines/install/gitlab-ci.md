# GitLab CI

There are two ways to set up Security Pipeline. One is to use it without cloning, and the other is to use it within your corporate GitLab.

### Pipelines usage without clonning

1. Set the following environment variables in the GitLab group where your repositories are located:
   * **`SEC_PORTAL_KEY`**: This is the authentication API token for the AppSec Portal. You can find it on the **Personal Info** page (requires authorization, see [this page](../../appsec-portal/install/) for more information).
   * **`SEC_DD_KEY`** and **`SEC_DD_URL`**: These are used if you want to integrate with **DefectDojo**. You can get the token from your DefectDojo instance.
   * **`SEC_MOBILE_MOBSF_URL`**: This is used if you want to use an external **MobSF** (Mobile Security Framework).
2. Once you have set up these variables, you can trigger the pipelines.

### Pipelines usage in corporate GitLab

#### Setup

1. Create a shared group in your corporate GitLab.
2. Create a project in the shared group.
3. Push the project content to your project.
4. Edit the `common/variables.yml` file with the proper URLs in **`SEC_DD_URL`** and **`SEC_MOBILE_MOBSF_URL`** (if you want to use an _external MobSF_).
5. Edit the **`SEC_PATH_TO_IMAGES`** variable in `common/variables.yml` (this variable should point to the project path to the security images project).
6. Add the same value to the `pipelines.yml` file to set the `.image` include directive properly. We will remove this step later. (_image_: `$CI_REGISTRY/whitespots-public/security-images/toolset:latest`)
7. Set the following environment variables in the GitLab group where your repositories are located:
   * **`SEC_PORTAL_KEY`**: This is the authentication API token for the AppSec Portal. You can find it on the **Personal Info** page (requires authorization, see [this page](../../appsec-portal/install/) for more information).
   * **`SEC_DD_KEY`**: used for **DefectDojo** integration. You can get the token from your DefectDojo instance.

> If you have any issues during installation or have any questions about using our pipelines, don't hesitate to reach out to our support team _**sales@whitespots.io**_ :heart:.
