---
title: Application Settings
book: integrations
chapter: okta
slug: okta-settings
weight: 11
---
Now that you have an application created, you will want to make sure to edit the **General** tab of this application, and then click on **Edit** button.

Within the **General Settings** of this new application, you need to change the **Login initiated by** dropdown to say **Either Okta or App**, and then click on both **Display application icon to users** and **Display application icon in the Okta Mobile app**

When you are done, your settings should look similar to the following.

![](/assets/img/integrations/okta/app-settings.png)

Make sure to press **Save** button to save these settings.

### Sign On Settings
After you have done this, you will now need to setup the **Sign On** credentials for the tokens generated by the OpenID connect. We need to ensure that the Groups are included within the tokens generated within the application. To do this, we need to go to the **Sign On** tab of your application.

Once you are on the **Sign On** section of your application, we need to click on the **Edit** button by the **OpenID Connect ID Token** section, and then we will need to change the following settings.

{: .table .table-bordered .table-striped}
| Setting | Value |
|---------|---------|
| Groups claim type | Filter |
| Groups claim filter: **Claim Name** | groups |
| Groups claim filter: **Type** | Regex |
| Groups claim filter: **Value** | .* |

When you are done, it should look like this.

![](/assets/img/integrations/okta/openid-token-claims.png)

### Assignments
Now that you have the Sign On Settings configured, you need to click on the **Assignments** section, and then ensure you have added your groups to the application. You can do this by clicking on the **Assign** button, and then say **Assign to Groups**, and then in the next dialog select the groups you wish to assign to the application.

![](/assets/img/integrations/okta/assign-to-groups.png)

Note: If you wish to add new groups to your Okta, you can click on the **Directory** section and then click on **Groups**. 

Make sure you take note of the names of these Groups that have been assigned since we will use this within our Form.io configurations to provide role mappings.

We are now ready to configure our **Form.io** project with our Okta configurations.