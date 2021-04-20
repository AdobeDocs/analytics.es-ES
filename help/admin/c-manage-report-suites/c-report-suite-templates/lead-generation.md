---
description: Define la configuración común de un sitio Web que proporciona información acerca de servicios y productos que normalmente se venden mediante un compromiso ulterior.
title: Generación de posibles clientes
feature: Admin Tools
uuid: e7d3cc4a-1bee-4722-92c1-4454f7613d39
exl-id: 4a629908-2bb4-4d61-a934-42906edff9df
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 100%

---

# Generación de posibles clientes

Define la configuración común de un sitio Web que proporciona información acerca de servicios y productos que normalmente se venden mediante un compromiso ulterior.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Caducidad | `s_code` campaign |
|---|---|---|---|---|---|
| Promoción interna | Cadena | Básica | Más reciente (última) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básica | Más reciente (última) | Visita | `evar2` |
| Tipo de evento autoservicio | Cadena | Básica | Más reciente (última) | Visita | `evar3` |

Esta plantilla de grupo de informes no tiene configurado ningún evento de éxito.

| Variables de perspectiva personalizada | `s_code` campaign |
|---|---|
| Seguro / No seguro | `prop1` |
| Propiedad de tráfico 2 a 5 | `prop2, prop3, prop4, prop5` |

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
