---
description: Las API de servicios web proporcionan acceso mediante programación a los informes de marketing y a otros servicios de Suite que permiten duplicar y aumentar la funcionalidad disponible a través de la interfaz de Analytics.
title: Servicios Web
feature: Company Settings
exl-id: d003d40e-b0b6-44f3-b9ef-ce6af61f5eb5
role: Admin
TQID: https://experienceleague.adobe.com/q0Ji-KYZJS486CKtHaDttXs3coS5hSYQd-cArPK1mCU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 42%

---

# Servicios Web

Las API de servicios web proporcionan acceso mediante programación a los informes de marketing y a otros servicios de Suite que permiten duplicar y aumentar la funcionalidad disponible a través de la interfaz de Analytics.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Configuración de la empresa]** > **[!UICONTROL Servicios web]** o **[!UICONTROL Acceso a la API]**


## API de Analytics 2.0

Para acceder a las API de Analytics 2.0, necesita el ID de compañía global de su compañía de Analytics. Puede encontrar el identificador de empresa global en **bold** en la parte superior de la sección [!UICONTROL Acceso a API]. Este es un ejemplo: &quot;El ID de empresa global de la empresa de Analytics en la que ha iniciado sesión actualmente es **adobe1234**&quot;.

## Administrar servicios de web heredados (obsoleto)

En [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html), puede actualizar los permisos para incluir a los usuarios que necesitan acceder a las API de servicios web.

## WSDL: descargue el archivo WSDL de la API de servicios web para los programadores de estos servicios

Visite [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/), que proporciona documentación, código de ejemplo y foros relacionados con las API de servicios web. Haga clic en Información general sobre las API de servicios web para obtener más información.

## Opciones de filtro

Al utilizar SOAP, si el analizador XML tiene problemas con caracteres no válidos o no válidos en las respuestas a llamadas a la API de servicios web, seleccione una o ambas de las siguientes opciones para que Analytics filtre automáticamente el resultado de la respuesta. Normalmente, este es un problema solo con los idiomas de doble byte (japonés, chino, coreano).

## Información de acceso a API

Ver información de acceso a servicios web por usuario. Esta tabla incluye el nombre de usuario y el secreto compartido de los servicios web, que los usuarios deben utilizar como parte del proceso de autenticación al realizar llamadas a los servicios web.

## Uso de token

Permite ver información sobre el número de tokens de servicios web que ha utilizado su empresa durante el mes natural actual.
