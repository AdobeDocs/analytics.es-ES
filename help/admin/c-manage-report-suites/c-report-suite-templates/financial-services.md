---
description: Define la configuración común de bancos y otras instituciones que proporcionan acceso a servicios en línea.
title: Servicios financieros
topic: Admin tools
uuid: a321b409-24a4-4d9f-9aac-65761261e991
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Servicios financieros

Define la configuración común de bancos y otras instituciones que proporcionan acceso a servicios en línea.

| Variables de conversión (eVars) | Tipo | Subrelaciones | Asignación | Vencimiento | `s_code` campaign |
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
| Instancias | Contador | N/D |
| Cierres de compra | Contador | `scCheckout` |
| Adiciones al carro de compras | Contador | `scAdd` |
| Eliminaciones del carro de compras | Contador | `scRemove` |
| Visitas | Contador (sin subrelaciones) | N/A |
| Vistas de páginas | Contador (sin subrelaciones) | N/A |
| Visitantes únicos diarios | Contador (sin subrelaciones) | N/A |
| Visitantes únicos | Contador (sin subrelaciones) | N/A |

