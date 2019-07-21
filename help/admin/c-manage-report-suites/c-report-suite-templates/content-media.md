---
description: Define la configuración común de un sitio web que desarrolla contenido original y muestra artículos y vídeos.
seo-description: Define la configuración común de un sitio web que desarrolla contenido original y muestra artículos y videos.
seo-title: Contenido y medios
solution: Analytics
title: Contenido y medios
topic: Herramientas de administración
uuid: 281 b 0 bf 8-59 dc -46 dc-b 5 d 5-5 e 42827 b 785 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Contenido y medios

Define la configuración común de un sitio web que desarrolla contenido original y muestra artículos y vídeos.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Vencimiento | `s_code` correspondiente |
|---|---|---|---|---|---|
| Campaña interna | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Variable de comercio 3 | Cadena | Básica | Más reciente (última) | Visita | `evar3` |
| Variable de comercio 4 | Cadena | Básica | Más reciente (última) | Visita | `evar4` |

| Eventos de éxito | Tipo | `s_code` correspondiente |
|---|---|---|
| Registros | Contador (sin subrelaciones) | `event1` |
| Registros de correo electrónico | Contador (sin subrelaciones) | `event2` |
| Suscripciones | Contador (sin subrelaciones) | `event3` |
| Vistas de páginas | Contador (sin subrelaciones) | `event4` |
| Impresiones de publicidad | Contador (sin subrelaciones) | `event5` |
| Clics en publicidad | Contador (sin subrelaciones) | `event6` |

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

