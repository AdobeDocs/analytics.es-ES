---
title: Recopilación de datos regionales
description: Información sobre la recopilación de datos regionales
translation-type: tm+mt
source-git-commit: 449a64e361523d7a68514d60541c443a4f696c9d

---


# Recopilación de datos regionales

Adobe Experience Cloud utiliza la recopilación de datos regionales (RDC) para que las interacciones entre los usuarios finales y Adobe Experience Cloud se produzcan lo más cerca posible de los usuarios finales. Esto mejora el rendimiento del sitio o la aplicación y garantiza que los datos se recopilen lo antes posible para optimizar la experiencia del usuario final. Una vez que los datos de sus propiedades digitales se recopilan a nivel regional en un centro de recopilación de datos (DCC), se reenvían a través de una conexión segura a un centro de procesamiento de datos (DPC) donde se procesan y se ponen a disposición de los productos de Adobe Experience Cloud.

Actualmente, la recopilación de datos regionales incluye las siguientes ubicaciones (sujetas a cambios):

## Recopilación de datos HTTP y de terceros

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Valor predeterminado | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. Puede determinarlo si ve alguno de estos puntos de conexión en la dirección URL de sus solicitudes.

## Recopilación de datos HTTPS de origen

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Global (predeterminado) | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |
| Solo para América | Oregón, Virginia |
| Sólo Europa | Irlanda, París |
| Sólo Asia Pacífico | Bombay, Singapur, Tokio, Sídney |

Nota: Experience Edge Global ofrece el mejor rendimiento para los usuarios finales.  Si desea utilizar un tipo de RDC alternativo, póngase en contacto con el servicio de atención al cliente de Adobe para obtener ayuda.

## Funcionamiento de la recopilación de datos regionales (RDC)

En la siguiente lista se describe el proceso de recopilación de datos que Adobe usa:

1. El DNS resuelve automáticamente la recopilación del nombre del host a la dirección IP del centro de recopilación de datos más cercano al visitante.
1. El visitante envía los datos a esa ubicación.
1. Los datos se reenvían inmediatamente a través de una conexión segura a un centro de procesamiento de datos, donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.

## Ventajas de la recopilación de datos regionales

| Ventaja | Descripción |
|---------|-----------|
| Rendimiento | Con RDC, los visitantes se conectarán al DCC más cercano. Esto significa que los tiempos de respuesta en su página se reducirán (cuanto menores sean, mejor), lo que dará como resultado un seguimiento más preciso y tiempos de carga más rápidos. |
| Redundancia | En caso de interrupción en la comunicación con un DCC, la recopilación de datos se enruta automáticamente al siguiente DCC más cercano, lo que garantiza la continuidad del servicio. |
| Redundancia | En caso de que se interrumpa la comunicación entre el centro de recogida de datos y el centro de procesamiento de datos, la infraestructura de recopilación de datos regionales de Adobe guarda los datos localmente y los reenvía al centro de procesamiento de datos cuando se restauran las comunicaciones. |

## Historial de revisión de documentación

| Actualización | Descripción |
|--------|---------|
| 4 de febrero de 2020 | Actualizar ubicaciones de RDC |
| 20 de febrero de 2019 | Reescritura completa. Se ha agregado información de red RDC. |
