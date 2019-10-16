---
description: En este documento se describe lo que debe hacer en Adobe Analytics para admitir los derechos de acceso CCPA y eliminación de los sujetos de datos.
seo-description: En este documento se describe lo que debe hacer en Adobe Analytics para admitir los derechos de acceso CCPA y eliminación de los sujetos de datos.
seo-title: Adobe Analytics y CCPA
title: Adobe Analytics y CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# Adobe Analytics y CCPA

En este documento se describe lo que debe hacer en Adobe Analytics para admitir los derechos de acceso CCPA y eliminación de los sujetos de datos.

## Descripción general de Adobe 

>[!IMPORTANT] El contenido de este documento no constituye asesoramiento jurídico y no está pensado para sustituir el asesoramiento jurídico. Consulte con el departamento legal de su empresa para obtener asesoramiento sobre la CCPA.

El 1 de enero de 2020 entra en vigor la Ley de Protección al Consumidor de California (CCPA). For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

Cuando Adobe proporciona software y servicios a una empresa, Adobe actúa como encargado del tratamiento de datos de cualquier dato personal que reciba y almacene en nombre de sus clientes, como parte de la prestación de los servicios. Como procesador de datos, Adobe procesa los datos personales de acuerdo con el permiso e instrucciones de su empresa (por ejemplo, según lo establecido en su acuerdo con Adobe).

Como responsable del tratamiento de datos, determinará qué datos personales Adobe trata y almacena en su nombre. Si usa soluciones de Adobe Experience Cloud, Adobe podría alojar datos personales en su nombre según las soluciones que use y la información que decida enviar a su cuenta de Adobe Experience Cloud. Si desea ver una lista de ejemplos, consulte [Privacidad de Adobe Experience Cloud.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## Cómo gestiona Adobe los datos de CCPA

Adobe Cloud Platform (ACP) proporciona una solución integrada que conecta la infraestructura de control de datos de su marca con las herramientas de Adobe que utiliza para crear y gestionar las experiencias de los consumidores. Las funciones de control de datos de Adobe Cloud Platform permiten vincular de forma directa las políticas de control al uso de los datos.

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe Experience Cloud Privacy Service API.

## Preparación de CCPA y sus datos de Adobe Analytics

En Adobe somos conscientes de que usted es quien más familiarizado está con los datos personalizados de sus grupos de informes y, por ello, le damos la oportunidad de definir su configuración y preferencias de control de datos.
To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. Puede identificar las columnas de su conjunto de datos que contengan datos directamente o indirectamente identificables, con lo que podrá presentar sus solicitudes de acceso y eliminación con respecto a esos datos. Para cada solicitud, se respetarán las etiquetas definidas en la interfaz de usuario de control de datos de Analytics del identificador específico con el que se corresponda dicha solicitud.

Consulte [Etiquetado de datos de grupos de informes](/help//admin/c-data-governance/gdpr-setup-reportsuite.md) para obtener más información sobre cómo configurar las etiquetas.

## Requisitos previos

* Familiarícese con la [terminología del RGPD.](/help/admin/c-data-governance/gdpr-terminology.md)
* Vincule su empresa de inicio de sesión a una organización de Experience Cloud, si no lo ha hecho ya. Póngase en contacto con el servicio de atención al cliente de Adobe y consulte [Organizaciones y vinculación de cuentas.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Asigne cualquier grupo de informes de Adobe Analytics que desee configurar para el control de datos a [su organización de Experience Cloud.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* Configure una directiva de retención de datos para cada grupo de informes de modo que se puedan cumplir las solicitudes de acceso y eliminación de CCPA.

   Adobe Analytics no puede ayudarle en el procesamiento de solicitudes a la API de Privacy Services, es decir, en el procesamiento de solicitudes de acceso o eliminación que reciba de sus usuarios finales, si el período de retención de datos no se ha establecido en Adobe Analytics. Póngase en contacto con su gestor de éxito de los clientes para establecer el periodo de retención de datos.

* Compruebe sus permisos: para utilizar la interfaz de gestión del control de datos en Adobe Analytics, debe ser administrador de Adobe Analytics.
* Considere implementar las variables [de administración de](/help/admin/c-data-governance/consent-variables.md) consentimiento para rastrear el estado de consentimiento en un nivel de visita individual.
