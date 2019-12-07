---
description: Varios informes de Adobe Analytics pueden mostrar No especificado, Otro o Desconocido, según el informe específico que se visualice. Por lo general, este elemento de línea significa que la variable no se definió o que de otro modo no estuvo disponible.
title: No especificado, Otro y Desconocido en los informes
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# "No especificado", "Otro" y "Desconocido" en los informes

Varios informes de Adobe Analytics pueden mostrar "No especificado", "Otro" o "Desconocido", según el informe específico que se visualice. Por lo general, este elemento de línea significa que la variable no se definió o que de otro modo no estuvo disponible. La siguiente es una lista completa de cómo cada informe puede tener alguno de estos elementos de línea.

## "No especificado" en informe

"No especificado" es un elemento de línea bastante común en los informes.

* **** Un evento se activa sin una variable de conversión: Por ejemplo: un usuario ingresa a su sitio y realiza una compra sin ningún valor de eVar1. Si ve pedidos usando la dimensión eVar1, no hay ningún valor al que atribuir este pedido. Por lo tanto, se atribuye automáticamente a "No especificado".
* **** Datos no clasificados en los informes de clasificación: Al ver los datos de clasificación, cualquier valor que no tenga datos asociados con esa clasificación en particular devuelve "No especificado". Para resolver este problema, clasifique el valor de la variable principal.
* **** Informes de desglose en los que solo se activó una variable: Cuando se aplica un desglose a una variable, se debe contabilizar cada instancia de esa variable. Si no se vio la segunda variable o si persistió desde una visita anterior, el valor de la dimensión es "No especificado".
* **** Visitas no móviles en informes de dispositivos móviles: Todas las visitas que no sean de dispositivos móviles en los informes móviles se muestran como "No especificado" ("No móvil" en Informes y análisis).

## Otro en informe

Aunque es algo raro en los informes, "Otro" puede ocurrir en varias circunstancias:

* **** Las páginas se activan fuera de los filtros de URL internos: Este valor está establecido para ayudar a protegerse contra el fraude de datos, como si otra organización roba el código fuente e lo implementa en su propio sitio. Para corregir este problema, asegúrese de que todas las direcciones URL en las que está implementado el código coincidan con los filtros de URL internos de la configuración del grupo de informes.
* **Visitantes con un navegador utilizado con poca frecuencia:** en el informe Tipos de explorador, aparece el estado Otro si los visitantes utilizan un navegador que no sea muy frecuente. Muchas organizaciones cuentan con uno propio. Todos los exploradores que las organizaciones más grandes no crearon se agrupan en "Otro" para evitar el desorden en los informes.

## Desconocido en informe

El estado Desconocido se puede producir bajo determinadas circunstancias:

* **** Visitas que no son de explorador al ver informes de tecnología: Si una biblioteca de AppMeasurement no puede determinar si una función es compatible, en los informes se muestra "Desconocido".
* **** Uso de segmentos en los que no se puede acceder a los componentes: Asegúrese de que las variables utilizadas en un segmento están habilitadas y de que los usuarios pueden acceder a ellas. Si un usuario no tiene acceso a un componente de segmento, o si una variable está deshabilitada, se muestra "Desconocido".

## Filtrado de estos valores en los informes {#section_5536E2B419D445D39C932E8F12C0070C}

En la mayoría de las circunstancias, estos elementos de línea se pueden ignorar con seguridad. El filtro de búsqueda puede utilizarse para eliminarlos si lo desea.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. Si un filtro de búsqueda no puede excluir datos, intente utilizar este valor (incluidos los dos puntos).
