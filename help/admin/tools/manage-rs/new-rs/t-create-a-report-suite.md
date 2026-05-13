---
description: Cree un contenedor básico para la recopilación de datos en Adobe Analytics
title: Crear un grupo de informes
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
TQID: https://experienceleague.adobe.com/ZmPcYHvXOhaXXnqsSVUh1bpvignxomS3d4S76iMCAa4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 313
ht-degree: 98%

---

# Crear un grupo de informes

Un grupo de informes es un silo de datos que Adobe Analytics utiliza para extraer informes. Una organización puede tener muchos grupos de informes, cada uno con diferentes conjuntos de datos. Aunque en el pasado era importante mantener grupos de informes separados, tener un único grupo de informes se ha vuelto más ventajoso. La introducción a los [grupos de informes virtuales](/help/components/vrs/vrs-about.md#virtual-report-suites) y el procesamiento del tiempo de los informes permite a los administradores crear sus propios subconjuntos de datos, lo que permite la flexibilidad de obtener datos globales y específicos del sitio.

Este artículo está diseñado para administradores de nivel de sistema o administradores de Adobe Analytics para prepararse para la recopilación de datos.

## Requisitos previos

[Guía de administración inicial de Adobe Analytics](/help/admin/admin-console/first-admin-guide.md): asegúrese de que un administrador de nivel de sistema le haya concedido acceso a Adobe Analytics a través de la Admin Console de Experience Cloud.

## Crear un grupo de informes {#create-report-suite}

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Haga clic en **[!UICONTROL Agregar grupo de informes]**.
1. Seleccione una plantilla predefinida o un grupo de informes existente para usar como [plantilla](/help/admin/tools/manage-rs/rs-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >Solo puede copiarse la configuración, no los datos. Si el Servicio de atención al cliente va a sobrescribir la configuración, deberá confirmar por escrito el descargo de responsabilidad con el que el Servicio de atención al cliente le informa de los riesgos. Véase [Configuración que no se copia desde un grupo de informes de origen](/help/admin/tools/manage-rs/new-rs/settings-not-copied-from-rs.md) para obtener más información.

1. Complete los campos descritos en [Nuevo grupo de informes](/help/admin/tools/manage-rs/new-rs/new-report-suite.md).
1. Haga clic en **[!UICONTROL Crear grupo de informes]**.

Una ID del grupo de informes tiene una longitud máxima de 40 bytes. Un nombre descriptivo del grupo de informes tiene una longitud máxima de 255 bytes.

## Resolución de problemas

**Tras iniciar sesión en Experience Cloud, el icono de Analytics aparece sombreado.**

Esto significa que no se han concedido a su cuenta los permisos correctos para Analytics. Colabore con un administrador de nivel de sistema de su organización para asegurarse de que cuenta con un perfil con los permisos adecuados para acceder a Adobe Analytics.

## Pasos siguientes

[Crear una propiedad de etiqueta de Adobe Analytics](/help/implement/launch/create-analytics-property.md): cree un área para administrar la implementación de Analytics.
