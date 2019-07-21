---
description: Para que los canales y sus datos puedan aparecer en el informe, debe crear los canales y las reglas subyacentes que procesan los datos. También puede crear importes de costos y presupuestos para los canales relacionados, y especificar cuánto tiempo desea que dure el período de compromiso del visitante. Las tareas de configuración de informes se realizan en las Herramientas de administración.
seo-description: Para que los canales y sus datos puedan aparecer en el informe, debe crear los canales y las reglas subyacentes que procesan los datos. También puede crear importes de costos y presupuestos para los canales relacionados, y especificar cuánto tiempo desea que dure el período de compromiso del visitante. Las tareas de configuración de informes se realizan en las Herramientas de administración.
seo-title: Acerca de los canales y las reglas
solution: Analytics
subtopic: Canales de mercadotecnia
title: Acerca de los canales y las reglas
topic: Reports and Analytics
uuid: 7 d 574790-4 d 0 d -419 d -8 fb 5-c 16 ec 5 a 4 a 387
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Acerca de los canales y las reglas

Para que los canales y sus datos puedan aparecer en el informe, debe crear los canales y las reglas subyacentes que procesan los datos. También puede crear importes de costos y presupuestos para los canales relacionados, y especificar cuánto tiempo desea que dure el período de compromiso del visitante. Las tareas de configuración de informes se realizan en las Herramientas de administración.

Imagine que el canal es un contenedor de visitas y que las reglas asignan las visitas al contenedor correspondiente.

![](assets/buckets_2.png)

Adobe ofrece varios canales predefinidos durante la [configuración automática](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B), que puede editar para adaptarlos a sus necesidades.

>[!NOTE]
>
>Adobe recomienda configurar el informe en un grupo de informes que puede utilizar como plantilla para realizar pruebas. Puede usar la plantilla para aplicar conjuntos de canales y reglas de forma global a uno o más grupos de informes de producción.
>
>Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

Consulte los siguientes temas:

* [Requisitos previos](../../components/c-marketing-channels/c-channels-rules.md#section_9913D2932E3140C099B7978CA95378B2)
* [Notas de procesamiento importantes](../../components/c-marketing-channels/c-channels-rules.md#section_DE372EEF02314F2395750CF2892DAAE1)

## Requisitos previos {#section_9913D2932E3140C099B7978CA95378B2}

En caso necesario, póngase en contacto con el departamento de atención al cliente para obtener ayuda con los requisitos previos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Configure el acceso del grupo de usuarios al **[!UICONTROL Informe de canal de mercadotecnia]**.

   See [Configure User Group Access](../../components/c-marketing-channels/t-user-groups.md#task_B156E7527FE94055A43A697338FE8C8C).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#section_DE372EEF02314F2395750CF2892DAAE1}

* El sistema procesa las reglas en el orden en el que las especifique y, cuando se cumple una regla, se detiene el procesamiento de las demás reglas.
* Las reglas pueden acceder a las variables que ha establecido VISTA, pero no pueden acceder a los datos que VISTA ha eliminado.
* Los canales almacenan solamente las métricas de conversión. Las métricas de tráfico no están disponibles.
* Dos canales de mercadotecnia nunca reciben crédito por el mismo evento (por ejemplo, compras o clics). En este sentido, los canales de mercadotecnia difieren de las eVars (ya que dos eVars pueden recibir crédito por el mismo evento).
* El informe puede procesar hasta 25 canales al mismo tiempo.

