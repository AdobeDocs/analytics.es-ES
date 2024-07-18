---
description: Vínculo a la API de administración de Adobe Analytics en github.
title: PREGUNTAS FRECUENTES SOBRE EL FIN DE LA VIDA ÚTIL DE API Adobe Analytics 1.4
feature: Admin Tools
role: Admin
source-git-commit: da96c049f7cfb73496416c2d8a7f4dcbc8f2303e
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 2%

---

# PREGUNTAS FRECUENTES SOBRE EL FIN DE LA VIDA ÚTIL DE API Adobe Analytics 1.4

## Aviso de fin de vida útil (EOL)

**¿Qué se va a retirar?**

* API de Adobe Analytics 1.4

* Autenticación WSSE de Adobe Analytics

**¿Cuándo se va a cerrar?**

Estos servicios se retirarán el 12 de agosto de 2026. Después de esta fecha ya no se podrá acceder a ellos.

## API 1.4

**¿Qué son estos servicios?**

Las [API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) son una colección de API que proporcionan una amplia gama de acciones, como informes, clasificaciones, fuentes de datos y configuraciones de grupos de informes.

**¿Qué debo hacer para migrar?**

Las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) ofrecen una ruta de migración hacia adelante para los usuarios de la API 1.4. Los clientes que actualmente utilizan las API 1.4 pueden migrar sus integraciones a las API 2.0 (las mismas API de las que depende la aplicación de Adobe Analytics) y aprovechar las últimas funciones.

Las API 2.0 le permiten realizar casi cualquier acción que pueda realizar en la interfaz de usuario de Analytics, como crear informes o administrar componentes como segmentos y métricas calculadas.

**¿Las API 2.0 ofrecen las mismas características que las API 1.4?**
Cualquier funcionalidad disponible en las API 1.4 se puede lograr usando las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). Algunas funcionalidades proporcionan las mismas capacidades que están disponibles en las API 1.4, y las mismas le permiten realizar casi cualquier acción que pueda realizar en la interfaz de usuario de Analytics, como crear informes o administrar componentes como segmentos y métricas calculadas.

## Autenticación WSSE

**¿Qué son estos servicios?**

La autenticación WSSE es un protocolo de autenticación heredado compatible con las API de Analytics 1.4. Se ha reemplazado por las opciones de autenticación basadas en OAuth que se proporcionan en [Adobe Developer Console](https://developer.adobe.com/console/home).

**¿Qué debo hacer para migrar?**

Los clientes de WSSE deben actualizar sus autenticaciones para utilizar las credenciales proporcionadas en Adobe Developer Console. Para ello, inicia sesión en [Adobe Developer Console](https://developer.adobe.com/console/home) para crear un proyecto para tu integración con la API de Analytics 2.0. Seleccione entre los métodos de autenticación de usuario de OAuth y de servidor a servidor de OAuth.

## Preguntas

P: **¿Afecta esto a mis proyectos existentes de E/S de Adobe para las API de Analytics?**

R: Todos los proyectos existentes que utilicen las API de Analytics 1.4 se verán afectados. Estas integraciones deben migrarse a las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) antes de la fecha límite de fin de vida.

P: **He compartido mis credenciales de Adobe con otro producto o aplicación que usa las API de Analytics. ¿Se han visto afectados?**

R: Si ese producto o aplicación utiliza sus credenciales de WSSE o llama a las API de Analytics 1.4, se verá afectado y deberá migrar antes de la fecha límite de fin de la vida útil. Póngase en contacto con el proveedor de productos o aplicaciones para obtener más detalles sobre sus planes de migración y plazos.

P: **No estoy seguro de qué API de Adobe Analytics estamos usando.**

R: Puede identificar a qué API está utilizando la dirección a la que se llama en la integración.

Para acceder a las API de Adobe Analytics 1.4, llame a cualquiera de las siguientes direcciones URL:
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

Se accede a las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) llamando a la siguiente URL:
* https://analytics.adobe.io

Si usa api*.omniture.com, debe migrar a las [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

P: **¿Las API de Adobe Analytics 2.0 son idénticas a las API 1.4? Si no es así, ¿cuáles son las principales diferencias?**

R: Las API de Adobe Analytics 2.0 no son idénticas a las API 1.4, pero ofrecen funciones comparables, incluidas las siguientes ventajas:

* Tiempos de respuesta más rápidos con métodos de consulta más sencillos y eficientes, lo que elimina la necesidad de sondear

* Capacidad programática para consultas y actualizaciones dinámicas de informes

* Gestión de errores más correcta

* Funcionamiento flexible para lograr cualquier cosa que pueda lograr con Analysis Workspace

* Coherencia y coincidencia de las llamadas de API a acciones de IU

* Acceso a todos los modelos de Attribution IQ utilizados en Analysis Workspace

* Acceso a todos los algoritmos de Detección de anomalías utilizados en Analysis Workspace

* La capacidad de integración con otros productos de Experience Cloud

* Mayor capacidad para varios informes de desglose

* Acceso a las últimas funciones de Analytics

La guía [Migración a las API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) analiza las diferencias clave entre las API 1.4 y 2.0. También encontrará información adicional en las [Preguntas frecuentes sobre la API de Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/).

P: **¿Afecta esto a la recopilación de datos?**

R: El fin de la vida útil de Adobe Analytics 1.4 no afecta a las soluciones de etiquetado, como Tags (anteriormente, Adobe Launch), WebSDK o AppMeasurement.js. Sin embargo, si utiliza las API de fuentes de datos o clasificaciones 1.4 para recopilar o mejorar los datos, debe migrar esos flujos de trabajo a las API de Adobe Analytics 2.0. Consulte la [Guía de extremos de API 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/) para obtener más información.

P: **¿Se ve afectada la API de inserción de datos?**

R: No, el EOL de Adobe Analytics 1.4 no afecta a la API de inserción de datos.

P: **¿Qué debo hacer si mi pregunta no fue respondida en esta pregunta frecuente?**

R: Si todavía tiene preguntas, póngase en contacto con el representante de su cuenta de Adobe.

