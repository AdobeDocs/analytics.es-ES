---
description: En este documento se describe lo que debe hacer en Adobe Analytics para cumplir los derechos de eliminación y acceso de sus interesados según la CCPA.
title: Adobe Analytics y la CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 95%

---

# Adobe Analytics y la CCPA

En este documento se describe lo que debe hacer en Adobe Analytics para cumplir los derechos de eliminación y acceso de sus interesados según la CCPA.

## Descripción general de Adobe

>[!IMPORTANT]
>
>El contenido de este documento no constituye asesoramiento jurídico y no está pensado para sustituir el asesoramiento jurídico. Consulte al departamento legal de su empresa para recibir consejos sobre la CCPA.

El 1 de enero de 2020 entra en vigor la Ley de Protección al Consumidor de California (CCPA). Para obtener más información sobre la respuesta de Adobe y lo que esto supone para usted como cliente de Adobe, consulte el [Centro de privacidad de Adobe.](https://www.adobe.com/es/privacy.html)

Cuando Adobe proporciona software y servicios a una empresa, Adobe actúa como encargado del tratamiento de datos de cualquier dato personal que reciba y almacene en nombre de sus clientes, como parte de la prestación de los servicios. Como procesador de datos, Adobe procesa los datos personales de acuerdo con los permisos e instrucciones que su empresa proporcione (y que pueden establecerse, por ejemplo, en el acuerdo entre su empresa y Adobe).

Como responsable del tratamiento de datos, determinará qué datos personales Adobe trata y almacena en su nombre. Si usa soluciones de Adobe Experience Cloud, Adobe podría alojar datos personales en su nombre según las soluciones que use y la información que decida enviar a su cuenta de Adobe Experience Cloud. Si desea ver una lista de ejemplos, consulte [Privacidad de Adobe Experience Cloud.](https://www.adobe.com/es/privacy/experience-cloud.html#collect)

## Cómo administra Adobe los datos de la CCPA

Adobe Cloud Platform (ACP) proporciona una solución integrada que conecta la infraestructura de control de datos de su marca con las herramientas de Adobe que utiliza para crear y gestionar las experiencias de los consumidores. Las funciones de control de datos de Adobe Cloud Platform permiten vincular de forma directa las políticas de control al uso de los datos.

Familiarícese con [cómo administra Adobe Analytics el RGPD](https://www.adobe.com/es/data-analytics-cloud/analytics/general-data-protection-regulation.html), donde se tratan los pasos de preparación para la privacidad y cómo llevar a cabo la integración con la API del servicio de privacidad de Adobe Experience Cloud.

## Preparación para la CCPA y sus datos de Adobe Analytics

En Adobe somos conscientes de que usted es quien más familiarizado está con los datos personalizados de sus grupos de informes y, por ello, le damos la oportunidad de definir su configuración y preferencias de control de datos.
Para ello, Adobe Analytics proporciona una interfaz de usuario de control de datos que le permite, como responsable del tratamiento de datos, establecer [etiquetas de privacidad](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels) en sus grupos de informes de Analytics y en todas las dimensiones de métricas de dichos grupos. Puede identificar las columnas de su conjunto de datos que contengan datos directamente o indirectamente identificables, con lo que podrá presentar sus solicitudes de acceso y eliminación con respecto a esos datos. Para cada solicitud, se respetarán las etiquetas definidas en la interfaz de usuario de control de datos de Analytics del identificador específico con el que se corresponda dicha solicitud.

Consulte [Etiquetar datos de grupos de informes](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md) para obtener más información sobre cómo configurar las etiquetas.

## Requisitos previos

* Familiarícese con la [terminología del RGPD.](/help/admin/c-data-governance/gdpr-terminology.md)
* Vincule su empresa de inicio de sesión a una organización de Experience Cloud, si no lo ha hecho ya. Póngase en contacto con el servicio de atención al cliente de Adobe y consulte [Organizaciones y vinculación de cuentas.](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=es)
* Establezca una política de retención de datos para cada grupo de informes a fin de poder satisfacer las solicitudes de acceso y eliminación de la CCPA.

  Adobe Analytics no puede ayudarle con el tratamiento de solicitudes en la API de los servicios de privacidad (es decir, el tratamiento de las solicitudes de acceso o eliminación que reciba de sus usuarios finales) si no se ha establecido el periodo de retención de datos en Adobe Analytics. Póngase en contacto con el equipo de su cuenta de Adobe para establecer el período de retención de datos.

* Compruebe sus permisos: para utilizar la interfaz de gestión del control de datos en Adobe Analytics, debe ser administrador de Adobe Analytics.
* Considere implementar las [Variables de administración de consentimiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) para rastrear el estado de consentimiento en un nivel de visita individual.
