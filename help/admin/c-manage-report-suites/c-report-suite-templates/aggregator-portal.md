---
description: Define la configuración común para un sitio Web que agrega contenido como, por ejemplo, un portal de noticias.
title: Portal de agregadores
feature: Admin Tools
uuid: d227c209-4d88-4eff-b126-994b2a179c51
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---

# Portal de agregadores

Define la configuración común para un sitio web que agrega contenido como, por ejemplo, un portal de noticias.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Caducidad | `s_code` campaign |
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
| Instancias | Contador | N/A |
| Cierres de compra | Contador | `scCheckout` |
| Adiciones al carro de compras | Contador | `scAdd` |
| Eliminaciones del carro de compras | Contador | `scRemove` |
| Visitas | Contador (sin subrelaciones) | N/D |
| Vistas de páginas | Contador (sin subrelaciones) | N/D |
| Visitantes únicos diarios | Contador (sin subrelaciones) | N/D |
| Visitantes únicos | Contador (sin subrelaciones) | N/D |
