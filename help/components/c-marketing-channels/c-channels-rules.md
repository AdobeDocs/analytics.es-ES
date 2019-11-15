---
description: Para que los canales y sus datos puedan aparecer en el informe, debe crear los canales y las reglas subyacentes que procesan los datos. También puede crear importes de costos y presupuestos para los canales relacionados, y especificar cuánto tiempo desea que dure el período de compromiso del visitante. Las tareas de configuración de informes se realizan en las Herramientas de administración.
solution: Analytics
subtopic: Marketing channels
title: Acerca de los canales y las reglas
topic: Reports and analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Acerca de los canales y las reglas

Para que los canales y sus datos puedan aparecer en el informe, debe crear los canales y las reglas subyacentes que procesan los datos. También puede crear importes de costos y presupuestos para los canales relacionados, y especificar cuánto tiempo desea que dure el período de compromiso del visitante. Las tareas de configuración de informes se realizan en las Herramientas de administración.

Imagine que el canal es un contenedor de visitas y que las reglas asignan las visitas al contenedor correspondiente.

![](assets/buckets_2.png)

Adobe ofrece varios canales predefinidos durante la [configuración automática](/help/components/c-marketing-channels/c-channel-autosetup.md), que puede editar para adaptarlos a sus necesidades.

>[!NOTE]
>
>Adobe recomienda configurar el informe en un grupo de informes que puede utilizar como plantilla para realizar pruebas. Puede usar la plantilla para aplicar conjuntos de canales y reglas de forma global a uno o más grupos de informes de producción.
>
>Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](/help/components/c-marketing-channels/t-template.md).

Consulte los siguientes temas:

* [Requisitos previos](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [Notas de procesamiento importantes](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## Requisitos previos {#prereqs}

En caso necesario, póngase en contacto con el departamento de atención al cliente para obtener ayuda con los requisitos previos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Configure el acceso del grupo de usuarios al **[!UICONTROL Informe de canal de mercadotecnia]**.

   See [Configure User Group Access](/help/components/c-marketing-channels/t-user-groups.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#important-proc-rules}

* El sistema procesa las reglas en el orden en el que las especifique y, cuando se cumple una regla, se detiene el procesamiento de las demás reglas.
* Las reglas pueden acceder a las variables que ha establecido VISTA, pero no pueden acceder a los datos que VISTA ha eliminado.
* Los canales almacenan solamente las métricas de conversión. Las métricas de tráfico no están disponibles.
* Dos canales de mercadotecnia nunca reciben crédito por el mismo evento (por ejemplo, compras o clics). En este sentido, los canales de mercadotecnia difieren de las eVars (ya que dos eVars pueden recibir crédito por el mismo evento).
* El informe puede procesar hasta 25 canales al mismo tiempo.

