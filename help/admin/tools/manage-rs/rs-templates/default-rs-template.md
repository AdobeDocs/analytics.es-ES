---
description: Configura distintas variables comunes y eventos de éxito de un sitio Web.
title: Plantilla predeterminada
feature: Report Suite Settings
uuid: edcf1b97-4ff2-4e98-b84c-199af2181d68
exl-id: 36aaded4-5c46-41af-a5c6-216bd2fcadb2
TQID: https://experienceleague.adobe.com/Tz2kROFW9n8apieb-bLIEPJ26LsZIhci5Azf1dvxRLI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 205
ht-degree: 71%

---

# Plantilla predeterminada

Configura distintas variables comunes y eventos de éxito de un sitio Web.

| Variables de conversión | Tipo | Subrelaciones | Asignación | Caducidad | `s_code` campaign |
|---|---|---|---|---|---|
| Campaña interna | Cadena | Básico | Más reciente (último) | Visita | `evar1` |
| Términos de búsqueda interna | Cadena | Básico | Más reciente (último) | Visita | `evar2` |
| Variable Commerce 3 | Cadena | Básico | Más reciente (último) | Visita | `evar3` |
| Variable Commerce 4 | Cadena | Básico | Más reciente (último) | Visita | `evar4` |

| Eventos de éxito | Tipo | `s_code` campaign |
|---|---|---|
| Registros | Contador (sin sub-relaciones) | `event1` |
| Registros de correo electrónico | Contador (sin sub-relaciones) | `event2` |
| Suscripciones | Contador (sin sub-relaciones) | `event3` |
| Vistas de páginas | Contador (sin sub-relaciones) | `event4` |
| Impresiones de publicidad | Contador (sin sub-relaciones) | `event5` |
| Clics en publicidad | Contador (sin sub-relaciones) | `event6` |

| Variables de perspectiva personalizada | `s_code` campaign |
|---|---|
| Propiedad de tráfico 1 a 5 | `prop1, prop2, prop3, prop4, prop5` |

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
