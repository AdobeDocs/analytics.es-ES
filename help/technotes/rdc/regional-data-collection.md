---
title: Recopilación de datos regionales
description: Información sobre la recopilación de datos regionales
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 1cf95a2bf57aacd6b0b5bdb1c3bf31d1b31339e0
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 74%

---

# Recopilación de datos regionales

Adobe Experience Cloud utiliza la recopilación de datos regionales (RDC) para que las interacciones entre los usuarios finales y Adobe Experience Cloud se produzcan lo más cerca posible de los usuarios finales. Esto mejora el rendimiento de su sitio y de la aplicación y garantiza que los datos se recopilen lo más rápidamente posible para optimizar la experiencia del usuario final. Una vez que los datos de sus propiedades digitales se recopilan a nivel regional en un centro de recopilación de datos (DCC, Data Collection Center), estos se envían a través de una conexión segura a un centro de procesamiento de datos (DPC, Data Processing Center), donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.

>[!IMPORTANT]
>
>El paquete de complementos de recopilación de datos regionales de China (China Performance Optimization) es un complemento facturable de Adobe Analytics. La optimización del rendimiento del Adobe en China continental permite a los clientes con usuarios dentro de China que envíen esos datos directamente al nodo perimetral de China, en lugar de a otras ubicaciones globalmente. Esto mejora los tiempos de carga de página y la precisión de los datos en comparación con el envío de estos a nodos fuera de China. Para obtener más información, póngase en contacto con el representante de ventas de Adobe.

Actualmente, la recopilación de datos regionales incluye las siguientes ubicaciones (sujetas a cambios):

## Recopilación de datos de terceros

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Predeterminado | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney, China* |

* La recopilación de datos regionales de China requiere el uso del paquete de complementos para China. Consulte la nota “Importante” anterior.

>[!NOTE]
>
>Si la solicitud de imagen de Analytics se envía al `adobedc`, `2o7.net` o `omtrdc.net` extremos y, a continuación, tiene una recopilación de datos de terceros. Puede determinarlo si ve alguno de estos puntos de conexión en la dirección URL de sus solicitudes.

## Recopilación de datos propia

| Tipo de RDC | Centros de recopilación de datos |
|---------------------|-------------------|
| Global (predeterminado) | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |
| Global + China* | China*, Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |
| Solo para América del Norte y América del Sur | Oregón, Virginia |
| Solo Europa | Irlanda, París |
| Solo Asia-Pacífico | Mumbai, Singapur, Tokio, Sydney |
| Solo para China* | Pekín |

*Los tipos de RDC Solo China y Global + China requieren el paquete de complementos de China. Consulte la nota “Importante” anterior. Global + China enrutará los datos que se originen dentro de China a nuestra RDC de China mientras enrutan los datos que se originan fuera de China a la RDC más cercana fuera de China.

>[!NOTE]
>
>Experience Edge Global ofrece el mejor rendimiento para sus usuarios finales.  Si desea utilizar un tipo de RDC alternativo, póngase en contacto con el servicio de atención al cliente de Adobe para obtener ayuda.

## Ventajas de la recopilación de datos regionales

| Ventaja | Descripción |
| --- | --- |
| Rendimiento | Con la recopilación de datos regionales, los visitantes se conectan al centro de recogida de datos más cercano. Esto proporciona el tiempo de respuesta más rápido, lo que da como resultado un seguimiento más preciso y tiempos de carga más rápidos. |
| Redundancia | En caso de que se interrumpa la comunicación entre el centro de recogida de datos y el centro de procesamiento de datos, la infraestructura de recopilación de datos regionales de Adobe guarda los datos localmente y los reenvía al centro de procesamiento de datos cuando se restauran las comunicaciones. |

## Funcionamiento de la recopilación de datos regionales (RDC)

En la siguiente lista se describe el proceso de recopilación de datos que Adobe usa:

1. El DNS resuelve automáticamente la recopilación del nombre del host a la dirección IP del centro de recopilación de datos más cercano al visitante.
1. El visitante envía los datos a esa ubicación.
1. Los datos se reenvían inmediatamente a través de una conexión segura a un centro de procesamiento de datos, donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.
