---
description: Varios informes de Adobe Analytics pueden mostrar No especificado, Otros o Desconocido, según el informe específico visto. Generalmente, este elemento de línea significa que la variable no se definió o que no estaba disponible.
seo-description: Varios informes de Adobe Analytics pueden mostrar No especificado, Otros o Desconocido, según el informe específico visto. Generalmente, este elemento de línea significa que la variable no se definió o que no estaba disponible.
seo-title: No especificado, Otros y Desconocido en los informes
solution: Analytics
title: No especificado, Otros y Desconocido en los informes
translation-type: tm+mt
source-git-commit: 5776b478580fea10a3a954f2e53048c3f0e1f9da

---


# No especificado, Otros y Desconocido en los informes

Varios informes de Adobe Analytics pueden mostrar No especificado, Otros o Desconocido, según el informe específico visto. Generalmente, este elemento de línea significa que la variable no se definió o que no estaba disponible. La siguiente es una lista completa de cómo cada informe puede tener alguno de estos elementos de línea.

## 'No especificado' en los informes

'No especificado' es un elemento de línea bastante común en los informes.

* **Se activa un evento sin una variable de conversión:** Por ejemplo, un usuario entra en el sitio y realiza una compra sin ningún valor de evar 1. Si ve pedidos con la dimensión evar 1, no hay ningún valor para atribuir este pedido. Por lo tanto, se atribuye automáticamente a 'No especificado'.
* **Datos no clasificados en informes de clasificación:** Cuando se ven los datos de clasificación, cualquier valor que no tenga datos asociados con esa clasificación en concreto vuelve al estado "No especificado". Para resolver este problema, clasifique el valor de la variable principal.
* **Desglosar informes donde solo se ha activado una variable:** Cuando se aplica un desglose a una variable, se debe justificar cada instancia de esa variable. Si no se vio la segunda variable o si persistió de una visita anterior, el valor de dimensión es 'No especificado'.
* **Visitas no móviles en informes móviles:** Las visitas no pertenecientes a dispositivos portátiles en los informes móviles se muestran como 'No especificado' ('No móvil' en Informes y análisis).

## 'Otro' en los informes

Aunque es algo poco frecuente en los informes, se puede producir 'Otro' bajo varias circunstancias:

* **Las páginas se activan fuera de los filtros de URL internos:** Este valor sirve para ayudar contra el fraude de datos, como por ejemplo si otra organización robe el código fuente e lo implementa en su propio sitio. Para solucionar este problema, asegúrese de que todas las direcciones URL en las que esté implementado el código coinciden con los filtros de URL internos en la configuración del grupo de informes.
* **Visitantes con un navegador utilizado con poca frecuencia:** en el informe Tipos de explorador, aparece el estado 'Otro' si los visitantes utilizan un navegador que no sea muy frecuente. Muchas organizaciones cuentan con uno propio. Todos los exploradores que las organizaciones de mayor tamaño no crearon se incluyen en 'Otro' para evitar el desorden del informe.

## 'Desconocido' en los informes

«Desconocido» se puede producir en varias circunstancias:

* **Visitas que no son de explorador cuando se ven informes de tecnología:** Si una biblioteca de appmeasurement no puede determinar si se admite una característica, se muestra 'Desconocido' en los informes.
* **Uso de segmentos donde no se puede acceder a los componentes:** Asegúrese de que las variables utilizadas en un segmento están activadas y de que los usuarios tengan acceso a ellas. Si un usuario no tiene acceso a un componente de segmento o si se desactiva una variable, se muestra Desconocido.

## Filtrado de estos valores en los informes {#section_5536E2B419D445D39C932E8F12C0070C}

En la mayoría de las circunstancias, estos elementos de línea se pueden ignorar con seguridad. El filtro de búsqueda puede utilizarse para eliminarlos si lo desea.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. Si un filtro de búsqueda no puede excluir datos, intente utilizar este valor (incluidos los dos puntos).
