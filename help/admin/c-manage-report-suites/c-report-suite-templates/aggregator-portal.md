---
description: Define la configuración común para un sitio Web que agrega contenido como, por ejemplo, un portal de noticias.
seo-description: Define la configuración común para un sitio Web que agrega contenido como, por ejemplo, un portal de noticias.
seo-title: Portal de agregación
solution: Analytics
title: Portal de agregación
topic: Herramientas de administración
uuid: d 227 c 209-4 d 88-4 eff-b 126-994 b 2 a 179 c 51
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Portal de agregación

Define la configuración común para un sitio Web que agrega contenido como, por ejemplo, un portal de noticias.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Vencimiento | `s_code` correspondiente |
|---|---|---|---|---|---|
| Campaña interna | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Categoría de referencia | Cadena | Básica | Más reciente (última) | Visita | `evar3` |

| Eventos de éxito | Tipo | `s_code` correspondiente |
|---|---|---|
| Inicio de sesión | Contador (sin subrelaciones) | `event1` |
| Vista de referencia | Contador (sin subrelaciones) | `event2` |
| Clics de referencia | Contador (sin subrelaciones) | `event3` |

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

