---
description: Detalles del anuncio de fin de vida útil de la API de Adobe Analytics 1.4.
title: Preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 4%

---

# Preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4

Adobe planea retirar la API de Adobe Analytics 1.4 el **12 de agosto de 2026**. Después de esta fecha ya no se podrá acceder a ellos. Este anuncio tiene un impacto directo en lo siguiente:

* API de Adobe Analytics 1.4, excluida la API de inserción de datos
* Autenticación WSSE de Adobe Analytics

## API 1.4

Las [API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) proporcionan una amplia gama de acciones, como informes, clasificaciones, fuentes de datos y configuraciones de grupos de informes. Están quedando obsoletas en favor de las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). Las API 2.0 le permiten realizar casi cualquier acción que pueda realizar en la interfaz de usuario de Analytics, como crear informes o administrar componentes como segmentos y métricas calculadas.

Adobe ofrece una [ruta de migración](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) para los usuarios de la API 1.4. Puede migrar sus integraciones a las API 2.0 (las mismas API de las que depende la aplicación de Adobe Analytics) y aprovechar las últimas funciones. Cualquier funcionalidad disponible en las API 1.4 se puede realizar usando las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Autenticación WSSE

La autenticación WSSE es un protocolo de autenticación heredado compatible con las API de Analytics 1.4. Se ha reemplazado por las opciones de autenticación basadas en OAuth que se proporcionan en [Adobe Developer Console](https://developer.adobe.com/console/home). Los proyectos que utilizan la autenticación WSSE deben actualizar sus credenciales a las proporcionadas en Adobe Developer Console. Para ello, inicia sesión en [Adobe Developer Console](https://developer.adobe.com/console/home) para crear un proyecto para tu integración con la API de Analytics 2.0. Seleccione el método de autenticación de usuario de OAuth o de servidor a servidor de OAuth.

## Preguntas frecuentes

+++**¿Afecta esto a mis proyectos existentes de Adobe IO para las API de Analytics?**

Cualquier proyecto existente que utilice las API de Analytics 1.4 se verá afectado. Estas integraciones deben migrarse a las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) antes de la fecha límite de fin de vida.

+++

+++**He compartido mis credenciales de Adobe con otro producto o aplicación que usa las API de Analytics. ¿Se han visto afectados?**

Si ese producto o aplicación utiliza sus credenciales de WSSE o llama a las API de Analytics 1.4, se verá afectado y deberá migrar antes de la fecha límite de fin de vida útil. Póngase en contacto con el proveedor de productos o aplicaciones para obtener más detalles sobre sus planes de migración y plazos.

+++

+++**¿Cómo puedo determinar qué API usa mi proyecto?**

La dirección URL base a la que llama la API determina qué versión de API utiliza el proyecto. Las API de Adobe Analytics 1.4 utilizan las siguientes direcciones URL:
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

Las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) utilizan la siguiente URL:

* `https://analytics.adobe.io`

Si alguno de sus proyectos de API usa `api*.omniture.com`, usa las API de Adobe Analytics 1.4 y debe migrar a las API 2.0.

+++

+++**¿Afecta este fin de vida útil a la recopilación de datos?**

El fin de la vida útil de Adobe Analytics 1.4 no afecta a las soluciones de etiquetado, como Etiquetas (anteriormente Adobe Launch), Web SDK o AppMeasurement. Sin embargo, si utiliza las API de fuentes de datos o clasificaciones 1.4 para mejorar los datos, debe migrar esos flujos de trabajo a las API de Adobe Analytics 2.0.

La API de inserción de datos no se ve afectada por este anuncio de fin de vida útil. Aunque Adobe planea seguir admitiendo la API de inserción de datos, Adobe recomienda usar la [API de inserción de datos en lote](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) en su lugar.

+++

Si tiene más preguntas acerca de este anuncio de fin de vida útil que no ha respondido en esta página, póngase en contacto con el equipo de cuenta de Adobe.
