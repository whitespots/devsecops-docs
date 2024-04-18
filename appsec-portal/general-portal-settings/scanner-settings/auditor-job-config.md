# Auditor Job Config

When a scanner is added to the [Auditor jobs](../../../auditor/settings/jobs/), this section specifies its settings for running the Audit.

* **Shared Volume**: in activated position passes its scan results to the next jobs in the sequence

<figure><img src="../../../.gitbook/assets/scan job1.png" alt=""><figcaption></figcaption></figure>

* **Image**: contains the address of the job's image registry. \
  If you are using your own job, change the address of the registry and specify its credentials

<figure><img src="../../../.gitbook/assets/scan job2.png" alt=""><figcaption></figcaption></figure>

* **Run Command**: specifies the command code to run the scan. \
  If you are using your own command, you should specify the _**/data/**_ directory to save the report in, so that it can be sent to the Appsec Portal.

<figure><img src="../../../.gitbook/assets/scan job3.png" alt=""><figcaption></figcaption></figure>



* **Environment Variables**: environment variables to be used by the job are specified. \
  You can _**delete**_ a variable, _**mark**_ it _**as required**_, _**hide**_ it or _**add**_ additional environment variables if necessary

<figure><img src="../../../.gitbook/assets/scan job4.png" alt=""><figcaption></figcaption></figure>
