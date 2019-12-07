---
description: Define la configuración común para un sitio Web que agrega contenido como, por ejemplo, un portal de noticias.
title: Portal de agregadores
topic: Admin tools
uuid: d227c209-4d88-4eff-b126-994b2a179c51
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Portal de agregadores

Define la configuración común para un sitio Web que agrega contenido como, por ejemplo, un portal de noticias.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Vencimiento | `s_code` campaign |
|---|---|---|---|---|---|
| Campaña interna | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Categoría de referencia | Cadena | Básica | Más reciente (última) | Visita | `evar3` |

| Eventos de éxito | Tipo | `s_code` campaign |
|---|---|---|
| Inicio de sesión | Contador (sin subrelaciones) | `event1` |
| Vista de referencia | Contador (sin subrelaciones) | `event2` |
| Clics de referencia | Contador (sin subrelaciones) | `event3` |

| Variables de perspectiva personalizada | `s_code` campaign |
|---|---|
| Propiedad de tráfico 1 a 5 | `prop1, prop2, prop3, prop4, prop5` |

La tabla siguiente contiene una lista de los eventos de comercio estándar. La configuración inicial de estos eventos es idéntica en todas las plantillas de grupo de informes. Los eventos con una variable s_code N/A no necesitan configurarse, se suministran de manera automática.

| Eventos de comercio estándar | Tipo | `s_code` campaign |
|---|---|---|
| Ingresos | Contador | `purchase` |
| Pedidos | Contador | `purchase` |
| Unidades | Contador | `purchase` |
| Carros de compras | Contador | `scOpen` |
| Vistas del carro de compras | Contador | `scView` |
| Instancias | Contador | N/D |
| Cierres de compra | Contador | `scCheckout` |
| Adiciones al carro de compras | Contador | `scAdd` |
| Eliminaciones del carro de compras | Contador | `scRemove` |
| Visitas | Contador (sin subrelaciones) | N/A |
| Vistas de páginas | Contador (sin subrelaciones) | N/A |
| Visitantes únicos diarios | Contador (sin subrelaciones) | N/A |
| Visitantes únicos | Contador (sin subrelaciones) | N/A |

