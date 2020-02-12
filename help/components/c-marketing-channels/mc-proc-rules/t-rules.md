---
title: Creación de reglas de procesamiento para los canales de mercadotecnia
description: Cree reglas de procesamiento de canales de mercadotecnia que averigüen si la visita de un visitante cumple los criterios asignados a un canal.
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# Creación de reglas de procesamiento para los canales de mercadotecnia

Cree reglas de procesamiento de canales de mercadotecnia que averigüen si la visita de un visitante cumple los criterios asignados a un canal.

Este procedimiento emplea una regla de correo electrónico como ejemplo. En este ejemplo, se presupone que ha agregado un canal de correo electrónico a su lista de canales de la página Administrador de canales de mercadotecnia.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Selección de un grupo de informes.

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).

1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Resultado](assets/marketing_channel_rules.png)

1. En el **[!UICONTROL Add New Rule Set]** menú, seleccione **[!UICONTROL Email]**.

   Al hacerlo, no selecciona el canal, sino que selecciona una plantilla que rellena la regla con algunos parámetros necesarios.

   ![Resultado](assets/example_email.png)

   Utilice lógica booleana (instrucciones de if / then) para configurar una regla. Por ejemplo, en la regla de canal de correo electrónico, proporcione la configuración o la información resaltada en la siguiente instrucción de regla:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   En este ejemplo, *`<value>`* es el parámetro de cadena de consulta que usa en su campaña de correo electrónico, como *`eml`*.
1. Para continuar creando reglas, haga clic en **[!UICONTROL Add Rule]**.
1. Para priorizar las reglas, arrástrelas a la posición que corresponda.
1. Haga clic en **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes y ejemplos](/help/components/c-marketing-channels/mc-faq/c-faq.md)

