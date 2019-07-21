---
description: Configura distintas variables comunes y eventos de éxito de un sitio Web.
seo-description: Configura distintas variables comunes y eventos de éxito de un sitio Web.
seo-title: Plantilla predeterminada
solution: Analytics
title: Plantilla predeterminada
topic: Herramientas de administración
uuid: edcf 1 b 97-4 ff 2-4 e 98-b 84 c -199 af 2181 d 68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Plantilla predeterminada

Configura distintas variables comunes y eventos de éxito de un sitio Web.

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

