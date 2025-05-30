---
description: En este documento se describe lo que debe hacer en Adobe Analytics para cumplir los derechos de eliminación y acceso de sus interesados según el RGPD.
title: Adobe Analytics y el RGPD
feature: Data Governance
role: Admin
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: ht
source-wordcount: '580'
ht-degree: 100%

---

# Adobe Analytics y el RGPD

En este documento se describe lo que debe hacer en Adobe Analytics para cumplir los derechos de eliminación y acceso de sus interesados según el RGPD.

## Descripción general de Adobe {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>El contenido de este documento no constituye asesoramiento jurídico y no está pensado para sustituir el asesoramiento jurídico. Consulte al departamento legal de su empresa para recibir consejos sobre el RGPD.

El 25 de mayo de 2018, entró en vigor el Reglamento General de Protección de Datos (RGPD). Para obtener más información sobre la respuesta de Adobe y lo que esto supone para usted como cliente de Adobe, consulte [RGPD y tu negocio.](https://www.adobe.com/es/privacy/general-data-protection-regulation.html)

Cuando Adobe proporciona software y servicios a una empresa, Adobe actúa como encargado del tratamiento de datos de cualquier dato personal que reciba y almacene en nombre de sus clientes, como parte de la prestación de los servicios. Como procesador de datos, Adobe procesa los datos personales de acuerdo con los permisos e instrucciones que su empresa proporcione (y que pueden establecerse, por ejemplo, en el acuerdo entre su empresa y Adobe).

Como responsable del tratamiento de datos, determinará qué datos personales Adobe trata y almacena en su nombre. Si usa soluciones de Adobe Experience Cloud, Adobe podría alojar datos personales en su nombre según las soluciones que use y la información que decida enviar a su cuenta de Adobe Experience Cloud. Si desea ver una lista de ejemplos, consulte [Privacidad de Adobe Experience Cloud.](https://www.adobe.com/es/privacy/experience-cloud.html#collect)

![](assets/privacy_ready.png)

## Cómo administra Adobe los datos del RGPD {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Experience Cloud ofrece una solución integrada que conecta la infraestructura de gobernanza de datos de su marca con las herramientas de Adobe que utiliza para crear y administrar las experiencias de los consumidores. Las funciones de gobernanza de datos de Adobe Experience Cloud vinculan de forma directa las políticas de gobernanza de datos al uso de datos.

Descubra cómo Adobe Analytics [se adapta al Reglamento general de protección de datos (RGPD)](https://www.adobe.com/es/data-analytics-cloud/analytics/general-data-protection-regulation.html) y detalla los pasos de preparación para el RGPD y la integración de la API del RGPD de Adobe Experience Cloud.

## Preparación para el RGPD y sus datos de Adobe Analytics {#section_9A47CDCD614C42238F6E05CFF0180195}

En Adobe somos conscientes de que usted es quien más familiarizado está con los datos personalizados de sus grupos de informes y, por ello, le damos la oportunidad de definir su configuración y preferencias de gobernanza de datos.

Para ello, Adobe Analytics proporciona una interfaz de usuario de gobernanza de datos que le permite, como responsable del tratamiento de datos, establecer [etiquetas de privacidad](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels) en sus grupos de informes de Analytics y en todas las dimensiones de métricas de dichos grupos. Puede identificar las columnas de su conjunto de datos que contengan datos directamente o indirectamente identificables, con lo que podrá presentar sus solicitudes de acceso y eliminación con respecto a esos datos. Para cada solicitud, se respetarán las etiquetas definidas en la interfaz de usuario de gobernanza de datos de Analytics del identificador específico con el que se corresponda dicha solicitud.

Consulte [Etiquetado de datos de grupos de informes](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md) para obtener más información sobre cómo establecer las etiquetas.

## Requisitos previos {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Familiarícese con la [terminología del RGPD.](/help/admin/c-data-governance/gdpr-terminology.md)
* Vincule su empresa de inicio de sesión a una organización de Experience Cloud, si no lo ha hecho ya. Póngase en contacto con el servicio de atención al cliente de Adobe y consulte [Organizaciones y vinculación de cuentas.](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=es)
* Establezca una política de retención de datos para cada grupo de informes a fin de poder satisfacer las solicitudes de acceso y eliminación del RGPD.

  >[!NOTE]
  >
  >Adobe Analytics no puede ayudarle con el tratamiento de solicitudes en la API del RGPD (es decir, el tratamiento de las solicitudes de acceso o eliminación que reciba de sus usuarios finales) si no se ha establecido el periodo de retención de datos en Adobe Analytics. Póngase en contacto con su equipo de cuentas de Adobe para poder establecer el periodo de retención de datos.

* Compruebe sus permisos: para utilizar la interfaz de gestión de gobernanza de datos en Adobe Analytics, debe ser administrador de Adobe Analytics.

