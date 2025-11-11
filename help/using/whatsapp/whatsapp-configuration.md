---
solution: Journey Optimizer
product: journey optimizer
title: Configure the WhatsApp channel
description: Learn how to configure your environment to send WhatsApp messages with Journey Optimizer
feature: Whatsapp, Channel Configuration
role: Admin
level: Intermediate
exl-id: d1f40cd8-f311-4df6-b401-8858095cef3e
---
# Get started with WhatsApp configuration {#whatsapp-config}

Before sending your WhatsApp message, you must configure your Adobe Journey Optimizer environment and associate with your WhatsApp account. To perform this:

1. [Create your WhatsApp API credentials](#WhatsApp-credentials)
1. [Create your WhatsApp Webhooks](#WhatsApp-webhook)
1. [Create your WhatsApp configuration](#WhatsApp-configuration)

These steps must be performed by an Adobe Journey Optimizer [System Administrator](../start/path/administrator.md).

## Create WhatsApp API credentials {#whatsapp-credentials}

1. In the left rail, browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** and select the **[!UICONTROL API Credentials]** menu. Click the **[!UICONTROL Create new API credentials]** button.

1. Configure your API credentials, as detailed below:

    * **API Token**: Enter your API token. Learn more in [Meta Documentation](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)
    * **Business Account ID**: Enter the unique number related to your business portfolio. Learn more in [Meta Documentation](https://www.facebook.com/business/help/1181250022022158?id=180505742745347).

    ![](assets/whatsapp-api.png)

1. Click **[!UICONTROL Continue]**.

1. Choose the **WhatsApp Business Account** you want to connect to your WhatsApp API credentials.

    ![](assets/whatsapp-api-2.png)

1. Select the **Sender name** used to send your Whatsapp messages.

1. Your phone number settings is automatically filled:

    * **Quality Rating**: reflects customer feedback on messages sent in the past 24 hours.
        * Green: High quality
        * Yellow: Medium quality
        * Red: Low quality
        
        Learn more about [Quality rating](https://www.facebook.com/business/help/766346674749731#)

    * **Throughput**: indicates the rate at which your phone number can send messages.

1. Click **[!UICONTROL Submit]** when you finished the configuration of your API credentials.

After creating and configuring your API credential, you now need to create your Webhook for WhatsApp messages. [Learn more](#whatsapp-webhook)

## Create Webhook {#WhatsApp-webhook}

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_inbound_keyword_category"
>title="Inbound keyword category"
>abstract="<b>Opt-In</b>: sends your defined auto-response when a user subscribes. <br/><b>Opt-Out</b>: sends your defined auto-response when a user unsubscribes. <br/><b>Help</b>:  sends your defined auto-response when a user requests help or support. <br/><b>Default</b>: sends your fallback auto-response when no keywords match.."

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_inbound_keyword"
>title="Enter your keywords"
>abstract="You can define keywords to trigger specific auto-responses based on what users text. Keywords are not case-sensitive, e.g., stop and STOP are treated the same."

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_webhook_url"
>title="Callback URL"
>abstract="The validation request and webhook notifications for this object are sent to the specified URL."

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_verify_token"
>title="Verify Token"
>abstract="The token that Meta echoes back to confirm and verify the callback URL during the verification process."

>[!NOTE]
>
>Without specified opt-in or opt-out keywords, standard consent messages are not enabled.

>[!NOTE]
>
>Webhook configuration is required to gather the WhatsApp feedback data in the AJO reportig.

Once your WhatsApp API credentials have been successfully created, the next step is to create a webhook and configure your inbound settings.
Make sure to have the webhook configured in the WhatsApp application dashboard in the Meta UI as well.

1. In the left rail, navigate to **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]**, select the **[!UICONTROL WhatsApp Webhooks]** menu under **[!UICONTROL WhatsApp settings]**, and click the **[!UICONTROL Create Webhook]** button.

    ![](assets/webhook-1.png)

1. Enter a **[!UICONTROL Name]** for your webhook.

1. From the **[!UICONTROL Select configuration]** drop-down, select the [API Credentials](#whatsapp-credentials) you previously created.

    ![](assets/webhook-2.png)

1. Choose your **[!UICONTROL Inbound keyword category]** such as:

    * **[!UICONTROL Opt-in Keywords]**
    * **[!UICONTROL Opt-out Keywords]**
    * **[!UICONTROL Help Keywords]**

1. Enter your **[!UICONTROL Keywords]** and click ![add](assets/do-not-localize/Smock_AddCircle_18_N.svg).

    ![](assets/webhook-3.png)

1. From the **[!UICONTROL Reply Message]** field, enter the message sent when a configured keyword is received, or select a pre-defined option from the drop-down menu.

    ![](assets/webhook-4.png)

<!--
1. Click **[!UICONTROL View payload editor]** to validate and customize your request payloads. 
    
    You can dynamically personalize your payload using profile attributes, and ensure accurate data is sent for processing and response generation with the help of built-in helper functions.
-->
1. Click ![add](assets/do-not-localize/Smock_AddCircle_18_N.svg) to add additional **[!UICONTROL Inbound keyword]**.

1. Click **[!UICONTROL Submit]** when you finished the configuration of your WhatsApp Webhook.

1. In the **[!UICONTROL Webhooks]** menu, click the ![bin icon](assets/do-not-localize/Smock_Delete_18_N.svg) to delete your WhatsApp Webhook.

    ![](assets/webhook-5.png)

1. To modify existing configuration and access your **[!UICONTROL Webhook URL]** or **[!UICONTROL Webhook Verify toker]**, locate the desired Webhook and click the **[!UICONTROL Edit]** option to make the necessary changes.

1. Copy your **[!UICONTROL Webhook Verify toker]** generated here, then paste it into the Meta interface as part of your Webhook setup. 

    For detailed instructions on how and where to add this verification token, refer to [Meta documentation](https://developers.facebook.com/docs/graph-api/webhooks/getting-started#configure-webhooks-product).

1. Access and copy your new **[!UICONTROL Webhook URL]** from your previously submitted **[!UICONTROL WhatsApp Webhook]**.

    ![](assets/webhook-6.png)

Now that your Webhook is configured, you can create your WhatsApp configuration.

## Create WhatsApp configuration {#whatsapp-configuration}

1. In the left rail, browse to **[!UICONTROL Administration]** > **[!UICONTROL Channels]** and select **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]**. Click the **[!UICONTROL Create channel configuration]** button.

    ![](assets/whatsapp-config-1.png)

1. Enter a name and a description (optional) for the configuration, then select the WhatsApp channel.

    >[!NOTE]
    >
    > Names must begin with a letter (A-Z). It can only contain alpha-numeric characters. You can also use underscore `_`, dot`.` and hyphen `-` characters.

1. Select **[!DNL WhatsApp]** as your channel.

    ![](assets/whatsapp-config-2.png)

1. Select **[!UICONTROL Marketing action(s)]** to associate consent policies to the messages using this configuration. All consent policies associated with the marketing action are leveraged in order to respect the preferences of your customers. Learn more

1. Select the previously created **[!UICONTROL WhatsApp API configuration]**.

    ![](assets/whatsapp-config-3.png)

1. Enter the **[!UICONTROL Sender name]** ​you want to use for your communications.

1. Once all the parameters have been configured, click **[!UICONTROL Submit]** to confirm. You can also save the channel configuration as draft and resume its configuration later on.

1. Once the channel configuration has been created, it displays in the list with the **[!UICONTROL Processing]** status.

    >[!NOTE]
    >
    >If the checks are not successful, learn more on the possible failure reasons in [this section](../configuration/channel-surfaces.md).  

1. Once the checks are successful, the channel configuration gets the **[!UICONTROL Active]** status. It is ready to be used to deliver messages.

Once configured, you can leverage all out-of-the-box channel capabilities such as message authoring, personalization, link tracking, and reporting.

You are now ready to send WhatsApp messages with Journey Optimizer.


## How-to video {#video}

The video below shows how to set up the WhatsApp channel in Adobe Journey Optimizer.

+++ See video

>[!VIDEO](https://video.tv.adobe.com/v/3470268/?learn=on)

+++
