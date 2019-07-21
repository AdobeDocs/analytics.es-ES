---
title: Recopilación de datos regionales
seo-title: Recopilación regional de datos de Adobe Analytics
description: Información sobre la recopilación de datos regionales
seo-description: Información sobre la recopilación de datos regionales
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Recopilación de datos regionales

Obtenga más información sobre la recopilación de datos regionales (RDC) de y cómo cambiar la red de recopilación, en caso necesario.

Para mejorar el rendimiento de la recopilación de datos, todos los clientes de Adobe Experience Cloud se han convertido a la recopilación regional de datos (RDC) para que la recopilación se realice lo más cerca posible de los usuarios finales. Esto mejora el rendimiento del sitio o la aplicación y garantiza que los datos se recopilen lo más rápido posible para optimizar la experiencia del usuario final. Una vez que los datos de sus propiedades digitales se recopilan a nivel regional en un centro de recopilación de datos (DCC, Data Collection Center), estos se envían a través de una conexión segura a un centro de procesamiento de datos (DPC, Data Processing Center), donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud. La recopilación de datos regionales ha sido la opción predeterminada para las nuevas implementaciones desde 2009.

Actualmente, la recopilación de datos regionales incluye las siguientes ubicaciones (sujetas a cambios):

## Recopilación de datos de terceros

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Valor predeterminado | San José, Virginia, Londres, Singapur, Hong Kong, Sídney y Ámsterdam. |
| Solo China | Pekín |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. Puede determinarlo si ve alguno de estos puntos de conexión en la dirección URL de sus solicitudes.

## Recopilación de datos propia

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Standard | San José, Virginia, Londres, Singapur. |
| Todas | Standard Plus Hong Kong, Sídney, Ámsterdam |
| Sólo EE. UU. | San José y Virginia. |
| Solo EU | Londres y Ámsterdam. |
| Sólo india | Bombay |

## Funcionamiento de la recopilación de datos regionales (RDC)

En la siguiente lista se describe el proceso de recopilación de datos que Adobe usa:

1. El DNS resuelve automáticamente la recopilación del nombre del host a la dirección IP del centro de recopilación de datos más cercano al visitante.
1. El visitante envía los datos a esa ubicación.
1. Los datos se reenvían inmediatamente a través de una conexión segura a un centro de procesamiento de datos, donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.

## Ventajas de la recopilación de datos regionales

| Ventaja | Descripción |
|---------|-----------|
| Rendimiento | Con RDC, los visitantes se conectarán al DCC más cercano. Esto significa que los tiempos de respuesta en su página se reducirán (cuanto menores sean, mejor), lo que dará como resultado un seguimiento más preciso y tiempos de carga más rápidos. Puede consultar información más detallada sobre el tiempo de respuesta en Mejoras de rendimiento con RDC. |
| Redundancia | En caso de interrupción en la comunicación con un DCC, la recopilación de datos se enruta automáticamente al siguiente DCC más cercano a la continuidad del servicio. |
| Redundancia | En caso de que se interrumpa la comunicación entre el centro de recogida de datos y el centro de procesamiento de datos, la infraestructura de recopilación de datos regionales de Adobe guarda los datos localmente y los reenvía al centro de procesamiento de datos cuando se restauran las comunicaciones. |

## Historial de revisión de documentación

| Actualización | Descripción |
|--------|---------|
| 20 de febrero de 2019 | Reescritura completa. Se agregó información de red RDC. |
