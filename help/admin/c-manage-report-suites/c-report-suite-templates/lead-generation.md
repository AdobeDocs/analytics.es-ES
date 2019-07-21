---
description: Define la configuración común de un sitio Web que proporciona información acerca de servicios y productos que normalmente se venden mediante un compromiso ulterior.
seo-description: Define la configuración común de un sitio Web que proporciona información acerca de servicios y productos que normalmente se venden mediante un compromiso ulterior.
seo-title: Generación de posibles clientes
solution: Analytics
title: Generación de posibles clientes
topic: Herramientas de administración
uuid: e 7 d 3 cc 4 a -1 bee -4722-92 c 1-4454 f 7613 d 39
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Generación de posibles clientes

Define la configuración común de un sitio Web que proporciona información acerca de servicios y productos que normalmente se venden mediante un compromiso ulterior.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Vencimiento | `s_code` correspondiente |
|---|---|---|---|---|---|
| Promoción interna | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Tipo de evento autoservicio | Cadena | Básica | Más reciente (última) | Visita | `evar3` |

Esta plantilla de grupo de informes no tiene configurado ningún evento de éxito.

| Variables de perspectiva personalizada | `s_code` correspondiente |
|---|---|
| Seguro / No seguro | `prop1` |
| Propiedad de tráfico 2 a 5 | `prop2, prop3, prop4, prop5` |

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

