---
description: La integración de Conectores de datos para appfigures utiliza variables de Analytics para rastrear distintas métricas de appfigures.
seo-description: La integración de Conectores de datos para appfigures utiliza variables de Analytics para rastrear distintas métricas de appfigures.
seo-title: Variables de integración de Analytics
title: Variables de integración de Analytics
uuid: 08 d 5 b 714-1 c 97-4 be 6-aae 8-1 f 8192535425
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

La integración de Conectores de datos para appfigures utiliza variables de Analytics para rastrear distintas métricas de appfigures.

La siguiente tabla describe las variables de Analytics que se activan automáticamente para la integración de appfigures.

## Variables requeridas {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>Esta integración utiliza variables dedicadas para los datos de almacén de aplicaciones, por lo que no es necesario asignar eventos y variables de comercio personalizados.

| Tipo de variable | Nombre  | Método de obtención de datos | Descripción |
|---|---|---|---|
| eVar | ID de objeto de App Store | Importado desde appfigures. | Configure esta evar con la caducidad de visita, la asignación más reciente y las subrelaciones básicas. |
| event (numérico) | Descargas de App Store | Importado desde appfigures. | El número de descargas de aplicaciones móviles. |
| event (numérico) | Compras de App Store (en aplicación) | Importado desde appfigures. | Número de compras y suscripciones dentro de la aplicación. |
| event (numérico) | Clasificación de App Store | Importado desde appfigures. | Se utiliza para definir la métrica calculada appfigures promedio. No se utiliza directamente. |
| event (numérico) | Divisor de la clasificación de App Store | Importado desde appfigures. | Se utiliza para definir la métrica calculada appfigures promedio. No se utiliza directamente. |
| event (numérico) | Clasificación de App Store | Importado desde appfigures. | Se utiliza para definir la métrica calculada appfigures promedio. No se utiliza directamente. |
| event (numérico) | Divisor de la clasificación de App Store | Importado desde appfigures. | Se utiliza para definir la métrica calculada appfigures promedio. No se utiliza directamente. |
| event (currency) | Ingresos de App Store (en la aplicación) | Importado desde appfigures. | La cantidad de ingresos dentro de la aplicación menos la tarifa de la tienda. |
| event (currency) | Ingresos de App Store (uno desactivado) | Importado desde appfigures. | Los ingresos totales de las compras de la aplicación menos la tarifa de la tienda. |
| event (currency) | Derechos de autor de App Store (en aplicación) | Importado desde appfigures. | No se utiliza |
| event (currency) | Derechos de autor de App Store (uno desactivado) | Importado desde appfigures. | No se utiliza |

