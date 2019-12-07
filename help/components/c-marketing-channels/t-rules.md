---
description: Cree reglas de procesamiento de canales de mercadotecnia que averigüen si la visita de un visitante cumple los criterios asignados a un canal.
subtopic: Marketing channels
title: Creación de reglas de procesamiento para los canales de mercadotecnia
topic: Reports and analytics
uuid: 0e47634f-3c69-46db-8af4-8d0b3d15f7a8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Creación de reglas de procesamiento para los canales de mercadotecnia

Cree reglas de procesamiento de canales de mercadotecnia que averigüen si la visita de un visitante cumple los criterios asignados a un canal.

Este procedimiento emplea una regla de correo electrónico como ejemplo. En este ejemplo, se presupone que ha agregado un canal de correo electrónico a su lista de canales de la página Administrador de canales de mercadotecnia.

1. Haga clic en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.

   Si no se han definido canales en el grupo de informes, se abre la página [!UICONTROL Canales de mercadotecnia: configuración automática]. 

   Consulte [Ejecución de la configuración automática](/help/components/c-marketing-channels/c-channel-autosetup.md).

1. Haga clic en **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Canales de marketing]** &gt; **[!UICONTROL Reglas de procesamiento de canal de marketing]**.

   ![Resultado (](assets/marketing_channel_rules.png)

1. En el menú **[!UICONTROL Agregar nuevo conjunto de reglas]**, seleccione **[!UICONTROL correo electrónico]**.

   Al hacerlo, no selecciona el canal, sino que selecciona una plantilla que rellena la regla con algunos parámetros necesarios.

   ![Resultado (](assets/example_email.png)

   Utilice lógica booleana (instrucciones de if / then) para configurar una regla. Por ejemplo, en la regla de canal de correo electrónico, proporcione la configuración o la información resaltada en la siguiente instrucción de regla:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   En este ejemplo, *`<value>`* es el parámetro de cadena de consulta que usa en su campaña de correo electrónico, como *`eml`*.
1. Para continuar creando reglas, haga clic en **[!UICONTROL Agregar regla]**.
1. Para priorizar las reglas, arrástrelas a la posición que corresponda.
1. Haga clic en **[!UICONTROL Guardar.]**

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes y ejemplos](/help/components/c-marketing-channels/c-faq.md)

