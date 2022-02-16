---
description: Define la configuración común de un sitio web que desarrolla contenido original y muestra artículos y vídeos.
title: Contenido y medios
feature: Report Suite Settings
exl-id: 9983ff86-9341-4b01-b4f3-41042874a9fb
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 100%

---

# Contenido y medios

Define la configuración común de un sitio web que desarrolla contenido original y muestra artículos y vídeos.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Caducidad | `s_code` campaign |
|---|---|---|---|---|---|
| Campaña interna | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Variable de comercio 3 | Cadena | Básica | Más reciente (última) | Visita | `evar3` |
| Variable de comercio 4 | Cadena | Básica | Más reciente (última) | Visita | `evar4` |

| Eventos de éxito | Tipo | `s_code` campaign |
|---|---|---|
| Registros | Contador (sin subrelaciones) | `event1` |
| Registros de correo electrónico | Contador (sin subrelaciones) | `event2` |
| Suscripciones | Contador (sin subrelaciones) | `event3` |
| Vistas de páginas | Contador (sin subrelaciones) | `event4` |
| Impresiones de publicidad | Contador (sin subrelaciones) | `event5` |
| Clics en publicidad | Contador (sin subrelaciones) | `event6` |

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
| Visitas | Contador (sin subrelaciones) | N/D |
| Vistas de páginas | Contador (sin subrelaciones) | N/D |
| Visitantes únicos diarios | Contador (sin subrelaciones) | N/D |
| Visitantes únicos | Contador (sin subrelaciones) | N/D |
