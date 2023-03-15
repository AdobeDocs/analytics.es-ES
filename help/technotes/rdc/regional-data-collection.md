---
title: Recopilación de datos regionales
description: Información sobre la recopilación de datos regionales
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 8f02656820ed0b9201f29fc9dca6870e6f7fe8fd
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 37%

---

# Recopilación de datos regionales

Adobe Experience Cloud utiliza la recopilación de datos regionales (RDC) para que las interacciones entre los visitantes y el Adobe se produzcan lo más cerca posible de los visitantes. Una vez que los datos se recopilan a nivel regional en un centro de recopilación de datos (DCC), se envían a través de una conexión segura a un centro de procesamiento de datos (DPC). Después del procesamiento, los datos estarán disponibles para los productos de Adobe Experience Cloud.

El proceso de recopilación de datos regionales sigue los siguientes pasos:

1. DNS resuelve automáticamente el nombre de host de recopilación en la dirección IP del centro de recopilación de datos más cercano al visitante.
1. El visitante envía los datos a esa ubicación.
1. Los datos se reenvían inmediatamente a través de una conexión segura a un centro de procesamiento de datos, donde se procesan y se ponen a disposición de los productos en Adobe Experience Cloud.

El uso de la recopilación de datos regionales ofrece varias ventajas:

* **Rendimiento**: con la recopilación de datos regionales, los visitantes se conectan al centro de recogida de datos más cercano. Esta optimización proporciona el tiempo de respuesta más rápido, lo que da como resultado un seguimiento más preciso y tiempos de carga más rápidos.
* **Redundancia**: si se interrumpe la comunicación entre el centro de recogida de datos y el centro de procesamiento de datos, la infraestructura de recopilación de datos regionales de Adobe guarda los datos localmente y los reenvía al centro de procesamiento de datos cuando se restauran las comunicaciones.

Actualmente, la recopilación de datos regionales incluye las siguientes ubicaciones (sujetas a cambios):

## Recopilación de datos de terceros

| Tipo de RDC | Centros de recopilación de datos |
| --- | --- |
| Predeterminado | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney, China* |

{style="table-layout:auto"}

* La recopilación de datos regionales de China requiere el uso del paquete de complementos para China. Consulte [Optimización del rendimiento en China](#china-performance-optimization) más abajo.

>[!NOTE]
>
>La recopilación de datos de terceros se produce si su solicitud de imagen de Analytics se envía a los puntos de conexión `adobedc`, `2o7.net` o `omtrdc.net`. Puede determinarlas si ve alguno de estos puntos de conexión en la dirección URL de sus solicitudes.

## Recopilación de datos propia

| Tipo de RDC | Centros de recopilación de datos |
| --- | --- |
| Global (predeterminado) | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |
| Global + China* | China*, Oregón, Virginia, Irlanda, París, Bombay, Singapur, Tokio, Sídney |
| Solo para América del Norte y América del Sur | Oregón, Virginia |
| Solo Europa | Irlanda, París |
| Solo Asia-Pacífico | Mumbai, Singapur, Tokio, Sydney |
| Solo China* | Pekín |

{style="table-layout:auto"}

*Los tipos de RDC Solo China y Global + China requieren el paquete de complementos de China. Global + China enruta los datos que se originan dentro de China a la RDC de China de Adobe, mientras que los datos que se originan fuera de China a la RDC más cercana fuera de China. Consulte [Optimización del rendimiento en China](#china-performance-optimization) más abajo.

## Optimización del rendimiento en China

El paquete de complementos de recopilación de datos regionales de China (China Performance Optimization) es un complemento facturable de Adobe Analytics. La optimización del rendimiento de Adobe en China continental permite a los clientes de China enviar datos directamente a los servidores de recopilación de datos de Adobe en China, en lugar de a otras ubicaciones de todo el mundo. Esta optimización mejora los tiempos de carga de página y la precisión de los datos en comparación con el envío de estos a ubicaciones fuera de China. En última instancia, los datos se transfieren a uno de los centros de procesamiento de datos (DPC) de Adobe fuera de China. Póngase en contacto con el representante de ventas de Adobe para obtener más información.

>[!NOTE]
>
>El paquete de complementos de recopilación de datos regionales de China no es compatible con [SDK web](/help/implement/aep-edge/overview.md).

