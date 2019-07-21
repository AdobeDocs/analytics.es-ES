---
description: Define la configuración común de un sitio Web de comercio electrónico.
seo-description: Define la configuración común de un sitio Web de comercio electrónico.
seo-title: Comercio
solution: Analytics
title: Comercio
topic: Herramientas de administración
uuid: 85 fc 235 d -0180-4245-b 831-0243 ebe 3 c 40 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comercio

Define la configuración común de un sitio Web de comercio electrónico.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Vencimiento | `s_code` correspondiente |
|---|---|---|---|---|---|
| Promociones internas | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Categoría de comercialización | Cadena | Básica | Más reciente (última) | Visita | `evar3` |
| Variable de comercio 4 | Cadena | Básica | Más reciente (última) | Visita | `evar4` |
| Variable de comercio 5 | Cadena | Básica | Más reciente (última) | Visita | `evar5` |

| Eventos de éxito | Tipo | `s_code` correspondiente |
|---|---|---|
| Registros | Contador (sin subrelaciones) | `event1` |
| Eventos personalizados 1 a 5 | Contador (sin subrelaciones) | `event1, event2, event3, event4, event5` |

| Variables de perspectiva personalizada | `s_code` correspondiente |
|---|---|
| Propiedad de tráfico 1 a 5 | `prop1, prop2, prop3, prop4, prop5` |

La tabla siguiente contiene una lista de los eventos de comercio estándar. La configuración inicial de estos eventos es idéntica en todas las plantillas de grupo de informes. Los eventos con una variable s_code N/A no necesitan configurarse, se suministran de manera automática.

| Eventos de comercio estándar | Tipo | `s_code` correspondiente |
|---|---|---|
| Ingresos | Contador | `purchase` |
| Pedidos | Contador | `purchase` |
| Unidades | Contador | `purchase` |
| Carros de compras | Contador | `scOpen` |
| Vistas de carro de compras | Contador | `scView` |
| Instancias | Contador | N/A |
| Cierres de compra | Contador | `scCheckout` |
| Adiciones al carro de compras | Contador | `scAdd` |
| Eliminaciones del carro de compras | Contador | `scRemove` |
| Visitas | Contador (sin subrelaciones) | N/A |
| Vistas de páginas | Contador (sin subrelaciones) | N/A |
| Visitantes únicos diarios | Contador (sin subrelaciones) | N/A |
| Visitantes únicos | Contador (sin subrelaciones) | N.D. |

