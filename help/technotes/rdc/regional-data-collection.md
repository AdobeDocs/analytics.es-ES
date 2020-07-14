---
title: Recopilación de datos regionales
description: Información sobre la recopilación de datos regionales
translation-type: tm+mt
source-git-commit: 058516ed9fb6cf7e73df4001404da45fb527e568
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 86%

---


# Recopilación de datos regionales

Adobe Experience Cloud utiliza la recopilación de datos regionales (RDC) para que las interacciones entre los usuarios finales y Adobe Experience Cloud se produzcan lo más cerca posible de los usuarios finales. Esto mejora el rendimiento de su sitio y de la aplicación y garantiza que los datos se recopilen lo más rápidamente posible para optimizar la experiencia del usuario final. Una vez que los datos de sus propiedades digitales se recopilan a nivel regional en un centro de recopilación de datos (DCC, Data Collection Center), estos se envían a través de una conexión segura a un centro de procesamiento de datos (DPC, Data Processing Center), donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.

>[!IMPORTANT]
>
>El paquete de Añada de RDC de China (Optimización del rendimiento de China) es un complemento con cargo a Adobe Analytics. La optimización del rendimiento de Adobe en China continental permite a los clientes de China enviar datos directamente al nodo del borde de China, en lugar de hacerlo en otras ubicaciones del mundo. Esto mejora los tiempos de carga de la página y la precisión de los datos al enviar los datos a los nodos fuera de China. Póngase en contacto con su representante de ventas de Adobe para obtener más información.

Actualmente, la recopilación de datos regionales incluye las siguientes ubicaciones (sujetas a cambios):

## Recopilación de datos HTTP y de terceros

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Predeterminado | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |

Nota: La recopilación de datos de terceros se produce si su solicitud de imagen de Analytics se envía a los puntos de conexión `2o7.net` u `omtdrc.net`. Puede determinarlo si ve alguno de estos puntos de conexión en la dirección URL de sus solicitudes.

## Recopilación propia de datos HTTPS

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Global (predeterminado) | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |
| Solo para América del Norte y América del Sur | Oregón, Virginia |
| Solo Europa | Irlanda, París |
| Solo Asia-Pacífico | Mumbai, Singapur, Tokio, Sydney |

Nota: Experience Edge Global ofrece el mejor rendimiento para los usuarios finales.  Si desea utilizar un tipo de RDC alternativo, póngase en contacto con el servicio de atención al cliente de Adobe para obtener ayuda.

## Funcionamiento de la recopilación de datos regionales (RDC)

En la siguiente lista se describe el proceso de recopilación de datos que Adobe usa:

1. El DNS resuelve automáticamente la recopilación del nombre del host a la dirección IP del centro de recopilación de datos más cercano al visitante.
1. El visitante envía los datos a esa ubicación.
1. Los datos se reenvían inmediatamente a través de una conexión segura a un centro de procesamiento de datos, donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.

## Ventajas de la recopilación de datos regionales

| Ventaja | Descripción |
|---------|-----------|
| Rendimiento | Con RDC, los visitantes se conectarán al centro de recopilación de datos (DCC) más cercano. Esto significa que los tiempos de respuesta en su página se reducirán (cuanto menores sean, mejor), lo que dará como resultado un seguimiento más preciso y tiempos de carga más rápidos. |
| Redundancia | En caso de que se interrumpa la comunicación con un DCC, la recopilación de datos se envía automáticamente al DCC más cercano, lo que garantiza la continuidad del servicio. |
| Redundancia | En caso de que se interrumpa la comunicación entre el centro de recogida de datos y el centro de procesamiento de datos, la infraestructura de recopilación de datos regionales de Adobe guarda los datos localmente y los reenvía al centro de procesamiento de datos cuando se restauran las comunicaciones. |

## Historial de revisiones de documentación

| Actualización | Descripción |
|--------|---------|
| 4 de febrero de 2020 | Actualización de ubicaciones de RDC |
| 20 de febrero de 2019 | Reescritura completa. Se ha agregado información de red RDC. |
