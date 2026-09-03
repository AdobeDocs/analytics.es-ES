---
description: Define la configuración común de un portal de trabajo o sitio Web de búsqueda de empleo.
title: Portal de trabajo
feature: Report Suite Settings
exl-id: d2a03139-7a5d-47bd-a287-fbe83f4a99fd
TQID: https://experienceleague.adobe.com/OVG4imjeOn6ZbW5BzTXVgGvmeNRF8soe1ODrKkIWBVk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 178
ht-degree: 66%

---

# Portal de trabajo

Define la configuración común de un portal de trabajo o sitio Web de búsqueda de empleo.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Caducidad | `s_code` campaign |
|---|---|---|---|---|---|
| Promoción interna | Cadena | Básico | Más reciente (último) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básico | Más reciente (último) | Visita | `evar2` |
| Tipo de evento de autoservicio | Cadena | Básico | Más reciente (último) | Visita | `evar3` |

Esta plantilla de grupo de informes no configura eventos de éxito.

| Variables de perspectiva personalizada | `s_code` campaign |
|---|---|
| Seguro / No seguro | `prop1` |
| Propiedad de tráfico 2 a 5 | `prop2, prop3, prop4, prop5` |

La siguiente tabla contiene una lista de los eventos comerciales estándar. La configuración inicial de estos eventos es idéntica en todas las plantillas de grupos de informes. No es necesario configurar los eventos con una variable s_code de N/A, sino que se proporcionan automáticamente.

| Eventos estándar de Commerce | Tipo | `s_code` campaign |
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
| Visitas | Contador (sin sub-relaciones) | N/A |
| Vistas de páginas | Contador (sin sub-relaciones) | N/A |
| Visitantes únicos diarios | Contador (sin sub-relaciones) | N/A |
| Visitantes únicos | Contador (sin sub-relaciones) | N/A |
