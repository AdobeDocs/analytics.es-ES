---
description: Define la configuración común de un sitio Web de comercio electrónico.
title: Comercio
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 100%

---

# Comercio

Define la configuración común de un sitio Web de comercio electrónico.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Caducidad | `s_code` campaign |
|---|---|---|---|---|---|
| Promociones internas | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Categoría de comercialización | Cadena | Básica | Más reciente (última) | Visita | `evar3` |
| Variable de comercio 4 | Cadena | Básica | Más reciente (última) | Visita | `evar4` |
| Variable de comercio 5 | Cadena | Básica | Más reciente (última) | Visita | `evar5` |

| Eventos de éxito | Tipo | `s_code` campaign |
|---|---|---|
| Registros | Contador (sin subrelaciones) | `event1` |
| Eventos personalizados 1 a 5 | Contador (sin subrelaciones) | `event1, event2, event3, event4, event5` |

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
| Instancias | Contador | N/A |
| Cierres de compra | Contador | `scCheckout` |
| Adiciones al carro de compras | Contador | `scAdd` |
| Eliminaciones del carro de compras | Contador | `scRemove` |
| Visitas | Contador (sin subrelaciones) | N/A |
| Vistas de páginas | Contador (sin subrelaciones) | N/A |
| Visitantes únicos diarios | Contador (sin subrelaciones) | N/A |
| Visitantes únicos | Contador (sin subrelaciones) | N/A |
