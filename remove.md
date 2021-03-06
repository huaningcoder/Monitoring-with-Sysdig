---

copyright:
  years:  2018, 2020
lastupdated: "2020-01-29"

keywords: Sysdig, IBM Cloud, monitoring, delete instance

subcollection: Monitoring-with-Sysdig

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}

# Removing an instance
{: #remove}

You can remove an instance of the {{site.data.keyword.mon_full_notm}} service from the {{site.data.keyword.Bluemix}} UI or through the command line.
{:shortdesc}

When you remove an instance from the {{site.data.keyword.cloud_notm}}, consider the following information to tidy up:

1. Write down the list of sources that forward metrics to the {{site.data.keyword.mon_full_notm}} instance that you want to remove. You must remove the Sysdig agent from each source.
2. Remove permissions that are granted to users to work with the instance. 

    If you use an access group to manage permissions to access the instance, you must remove the access group.

    If you use an access group to manage permissions to access different service instances, you must remove the policies that grant permissions to the instance that you want to remove.
    
    If you grant individual policies to users, you must gather the information of each user that has access to the instance. Then, you must remove one by one the policies that relate to the instance that you want to delete.


Then, delete the instance from the {{site.data.keyword.cloud_notm}} Dashboard.


## Removing an instance through the {{site.data.keyword.cloud_notm}} UI
{: #remove_ui}

To remove an instance of {{site.data.keyword.mon_full_notm}} by using the {{site.data.keyword.cloud_notm}} UI, complete the following steps:

1. [Log in to your {{site.data.keyword.cloud_notm}} account ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com/login){:new_window}.

2. Click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) &gt; **Observability**. 

3. Select **Monitoring**. The list of the instances is displayed.

4. Select the instance that you want to delete.

5. From the *Action* menu, select **Remove**.


## Removing an instance through the CLI
{: #remove_cli}

To remove an instance of {{site.data.keyword.mon_full_notm}} through the command line, complete the following steps:

1. [Pre-requisite] [Installion of the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started). If the CLI is installed, continue with the next step.

2. Log in to the region in the {{site.data.keyword.cloud_notm}} where you want to provision the instance. Run the following command: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. Set the resource group where the instance is provisioned. Run the following command: [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    By default, the `default` resource group is set.

4. Remove the instance. Run the [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) command:

    ```
    ibmcloud resource service-instance-delete NAME --recursive
    ```
    {: codeblock}

    Where NAME is the name of the instance

    For example, to remove an instance, run the following command:

    ```
    ibmcloud resource service-instance-delete sysdig-instance-01 --recursive
    ```
    {: codeblock}

    The `--recursive` option is used to delete the service keys that were associated with the Sysdig instance.
    {: note}
    

