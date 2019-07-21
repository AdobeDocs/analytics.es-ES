---
description: En este documento se describe lo que debe hacer en Adobe Analytics para cumplir los derechos de eliminación y acceso de sus interesados según el RGPD.
seo-description: En este documento se describe lo que debe hacer en Adobe Analytics para cumplir los derechos de eliminación y acceso de sus interesados según el RGPD.
seo-title: Adobe Analytics y el RGPD
title: Adobe Analytics y el RGPD
uuid: 16 fd 5 af 8-9148-4 e 09-ad 54-9 e 3 cdd 2 b 3 c 6 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Adobe Analytics y el RGPD

En este documento se describe lo que debe hacer en Adobe Analytics para cumplir los derechos de eliminación y acceso de sus interesados según el RGPD.

## Descripción general de Adobe {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>El contenido de este documento no constituye asesoramiento jurídico y no está pensado para sustituir el asesoramiento jurídico. Consulte al departamento legal de su empresa para recibir consejos sobre el RGPD.

El 25 de mayo de 2018, entró en vigor el Reglamento General de Protección de Datos (RGPD) de la Unión Europea. Para obtener más información sobre la respuesta de Adobe y lo que esto supone para usted como cliente de Adobe, consulte [RGPD y tu negocio](https://www.adobe.com/privacy/general-data-protection-regulation.html).

Cuando Adobe proporciona software y servicios a una empresa, Adobe actúa como encargado del tratamiento de datos de cualquier dato personal que reciba y almacene en nombre de sus clientes, como parte de la prestación de los servicios. Como encargado del tratamiento de datos, Adobe trata los datos personales de conformidad con los permisos y las instrucciones de su empresa (por ejemplo, como se haya dispuesto en su contrato con Adobe).

Como controlador de datos, usted determina los datos personales que Adobe procesa y almacena en su nombre. Si usa soluciones de Adobe Experience Cloud, Adobe podría alojar datos personales en su nombre según las soluciones que use y la información que decida enviar a su cuenta de Adobe Experience Cloud. Si desea ver una lista de ejemplos, consulte [Privacidad de Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

![](assets/gdpr_ready.png)

## Cómo administra Adobe los datos del RGPD {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform (ACP) proporciona una solución integrada que conecta la infraestructura de control de datos de su marca con las herramientas de Adobe que utiliza para crear y gestionar las experiencias de los consumidores. Las funciones de control de datos de Adobe Cloud Platform permiten vincular de forma directa las políticas de control al uso de los datos.

Familiarícese con [cómo administra Adobe Analytics el RGPD](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html), donde se tratan los pasos de preparación para el RGPD y cómo llevar a cabo la integración con la API RGPD de Adobe Experience Cloud.

## Preparación para el RGPD y sus datos de Adobe Analytics {#section_9A47CDCD614C42238F6E05CFF0180195}

En Adobe somos conscientes de que usted es quien más familiarizado está con los datos personalizados de sus grupos de informes y, por ello, le damos la oportunidad de definir su configuración y preferencias de control de datos.

Para ello, Adobe Analytics proporciona una interfaz de usuario de control de datos que le permite, como responsable del tratamiento de datos, establecer [etiquetas de privacidad](../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2) en sus grupos de informes de Analytics y en todas las dimensiones de métricas de dichos grupos. Puede identificar las columnas de su conjunto de datos que contengan datos directamente o indirectamente identificables, con lo que podrá presentar sus solicitudes de acceso y eliminación con respecto a esos datos. Para cada solicitud, se respetarán las etiquetas definidas en la interfaz de usuario de control de datos de Analytics del identificador específico con el que se corresponda dicha solicitud.

Consulte [Etiquetado de datos de grupos de informes](../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731) para obtener más información sobre cómo configurar las etiquetas.

## Requisitos previos {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Familiarícese con la [terminología del RGPD](../../admin/c-data-governance/gdpr-terminology.md#concept_83C744A9D077476BAD8F8492DF68EBD7).
* Vincule su empresa de inicio de sesión a una organización de Experience Cloud, si no lo ha hecho ya. Póngase en contacto con el servicio de atención al cliente de Adobe y consulte [Organizaciones y vinculación de cuentas](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).
* Asigne cualquier grupo de informes de Adobe Analytics que desee configurar para el control de datos a [su organización de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* Establezca una política de retención de datos para cada grupo de informes a fin de poder satisfacer las solicitudes de acceso y eliminación del RGPD.

   >[!NOTE]
   >
   >Adobe Analytics no puede ayudarle a procesar solicitudes a la API del RGPD, es decir, a procesar el acceso o las solicitudes de eliminación recibidas de los usuarios finales, si el período de retención de datos no se ha establecido en Adobe Analytics. Póngase en contacto con su gestor de éxito de los clientes para establecer el periodo de retención de datos.

* Compruebe sus permisos: para utilizar la interfaz de gestión del control de datos en Adobe Analytics, debe ser administrador de Adobe Analytics.

