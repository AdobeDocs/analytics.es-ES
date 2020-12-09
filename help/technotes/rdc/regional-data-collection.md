---
title: Recopilación de datos regionales
description: Información sobre la recopilación de datos regionales
translation-type: tm+mt
source-git-commit: 731209e28dab9f17e06948614149a4c99938fdae
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 57%

---


# Recopilación de datos regionales

Adobe Experience Cloud utiliza la recopilación de datos regionales (RDC) para que las interacciones entre los usuarios finales y Adobe Experience Cloud se produzcan lo más cerca posible de los usuarios finales. Esto mejora el rendimiento de su sitio y de la aplicación y garantiza que los datos se recopilen lo más rápidamente posible para optimizar la experiencia del usuario final. Una vez que los datos de sus propiedades digitales se recopilan a nivel regional en un centro de recopilación de datos (DCC, Data Collection Center), estos se envían a través de una conexión segura a un centro de procesamiento de datos (DPC, Data Processing Center), donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.

>[!IMPORTANT]
>
>El paquete de Añada de China RDC (China Performance Optimization) es un complemento de pago para Adobe Analytics. La optimización del rendimiento de Adobe en China continental permite a los clientes dentro de China enviar datos directamente al nodo del borde de China, en lugar de hacerlo en otras ubicaciones a nivel mundial. Esto mejora los tiempos de carga de la página y la precisión de los datos al enviar los datos a los nodos fuera de China. Para obtener más información, póngase en contacto con el representante de ventas de Adobe.

Actualmente, la recopilación de datos regionales incluye las siguientes ubicaciones (sujetas a cambios):

## Recopilación de datos HTTP y de terceros

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Predeterminado | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney, China* |

Note: If your Analytics image request is sent to the `adobedc`, `2o7.net` or `omtrdc.net` endpoints, then you have third-party data collection. Puede determinarlo si ve alguno de estos puntos de conexión en la dirección URL de sus solicitudes.

*China RDC requiere el paquete de Añado para China. Consulte la nota &#39;Importante&#39; anterior.

## Recopilación propia de datos HTTPS

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Global (predeterminado) | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |
| Solo para América del Norte y América del Sur | Oregón, Virginia |
| Solo Europa | Irlanda, París |
| Solo Asia-Pacífico | Mumbai, Singapur, Tokio, Sydney |
| Solo en China* | Pekín |

*China RDC requiere el paquete de Añado para China. Consulte la nota &#39;Importante&#39; anterior.

Nota: Experience Edge Global ofrece el mejor rendimiento para los usuarios finales.  Si desea utilizar un tipo de RDC alternativo, póngase en contacto con el Servicio de atención al cliente de Adobe para obtener ayuda.

## Ventajas de la recopilación de datos regionales

| Ventaja | Descripción |
| --- | --- |
| Rendimiento | Con RDC, sus visitantes se conectarán al DCC más cercano. Esto proporciona el tiempo de respuesta más rápido, lo que resulta en un seguimiento más preciso y tiempos de carga más rápidos. |
| Redundancia | En caso de interrupción en la comunicación con un DCC, la recopilación de datos se enruta automáticamente al siguiente DCC más cercano, lo que garantiza la continuidad del servicio. |
| Redundancia | En caso de interrupción de la comunicación entre el DCC y su DPC, la infraestructura RDC de Adobe guarda los datos localmente y luego los reenvía al DPC cuando se restauran las comunicaciones. |

## Funcionamiento de la recopilación de datos regionales (RDC)

En la siguiente lista se describe el proceso de recopilación de datos que Adobe usa:

1. El DNS resuelve automáticamente la recopilación del nombre del host a la dirección IP del centro de recopilación de datos más cercano al visitante.
1. El visitante envía los datos a esa ubicación.
1. Los datos se reenvían inmediatamente a través de una conexión segura a un centro de procesamiento de datos, donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.
