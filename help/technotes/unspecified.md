---
description: Varios informes de Adobe Analytics pueden mostrar No especificado, Ninguno, Otro o Desconocido según el informe específico que se visualice. En general, este elemento de línea indica que la variable no se definió o que no estuvo disponible.
title: No especificado, Ninguno, Otro y Desconocido en los informes
translation-type: ht
source-git-commit: fc54cb27f365015b6c7716d68bfc4cbe80b40b8b
workflow-type: ht
source-wordcount: '515'
ht-degree: 100%

---


# “No especificado”, “Ninguno”, “Otro” y “Desconocido” en los informes

Varios informes de Adobe Analytics pueden mostrar “No especificado”, “Otro” o “Desconocido” según el informe específico que se visualice. En general, este elemento de línea indica que la variable no se definió o que no estuvo disponible. La siguiente es una lista completa de cómo cada informe puede tener alguno de estos elementos de línea.

## “No especificado” (o “Ninguno”) en los informes

“No especificado” es un elemento de línea bastante común en los informes. También se refiere a él con frecuencia como “Ninguno”.

* **Un evento se activa sin una variable de conversión:** por ejemplo, un usuario visita su sitio y realiza un compra sin ningún valor eVar1. Si ve los pedidos mediante la dimensión eVar1, comprobará que no hay ningún valor al que atribuir este pedido. Por lo tanto, se atribuye automáticamente al estado “No especificado”.
* **Datos no clasificados en los informes de clasificación:** cuando se ven los datos de clasificación, cualquier valor que no tenga datos asociados con esa clasificación en concreto vuelve al estado “No especificado”. Para resolver este problema, clasifique el valor de la variable principal.
* **Informes de desglose en los que solo se activó una variable:** cuando se aplica un desglose a una variable, se debe contabilizar cada instancia de dicha variable. Si no se vio la segunda variable o si persistió desde una visita anterior, el elemento de la dimensión será “No especificado”.
* **Visitas que no son de móviles en los informes de dispositivos móviles:** todas las visitas que no sean de dispositivos móviles se muestran en los informes móviles como “No especificado” (“No móvil” en Reports and Analytics).

## “Otro” en un informe

A pesar de que no sea muy frecuente en los informes, el estado “Otro” se puede producir en determinadas circunstancias:

* **Las páginas se activan fuera de los filtros de URL internos:** este valor se establece como barrera de protección contra el robo de datos. Un ejemplo de dicha práctica sería si otra organización robase el código fuente y lo implementase en su propio sitio. Para corregir este problema, asegúrese de que todas las URL en las que está implementado su código coinciden con los filtros de URL internos en la configuración del grupo de informes.
* **Visitantes con un navegador utilizado con poca frecuencia:** en el informe Tipos de explorador, aparece el estado “Otro” si los visitantes utilizan un navegador que no sea muy frecuente. Muchas organizaciones cuentan con uno propio. Todos los exploradores que no hayan creado las organizaciones más grandes se agrupan en “Otro” para evitar el desorden de los informes.

## “Desconocido” en un informe

El estado “Desconocido” se puede producir bajo determinadas circunstancias:

* **Visitas que no son de explorador al ver informes de tecnología:** si una biblioteca de AppMeasurement no puede determinar si una función es compatible, en los informes se muestra “Desconocido”.
* **Uso de segmentos en los que no se puede acceder a los componentes:** asegúrese de que las variables utilizadas en un segmento estén habilitadas y de que los usuarios puedan acceder a ellas. Si un usuario no tiene acceso a un componente de segmento, o si una variable está deshabilitada, se muestra “Desconocido”.

## Filtrado de estos valores en los informes {#section_5536E2B419D445D39C932E8F12C0070C}

En la mayoría de las circunstancias, estos elementos de línea se pueden ignorar con seguridad. El filtro de búsqueda puede utilizarse para eliminarlos si lo desea.

Algunas variables de datos de servidor utilizan el valor `::unspecified::` en los informes, aunque esto no aparece en la interfaz. Si un filtro de búsqueda no puede excluir datos, pruebe a utilizar este valor (incluidos los dos puntos).
