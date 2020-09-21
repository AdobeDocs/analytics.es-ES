---
title: Anulaciones de variables
description: Las anulaciones de variables permiten cambiar el valor de una variable para un único seguimiento o una sola llamada de seguimiento de vínculos.
translation-type: ht
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de
workflow-type: ht
source-wordcount: '106'
ht-degree: 100%

---


# Anulaciones de variables

Las sobrescrituras de variables le permiten cambiar los valores de Analytics para una sola visita sin afectar a las variables existentes en la página.

## Flujo de trabajo

1. Cree un nuevo objeto de JavaScript. El nombre del objeto puede ser lo que desee.

   ```js
   var y = new Object();
   ```

2. Asignar propiedades válidas de Analytics a este objeto:

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. Utilice el objeto como argumento dentro de la llamada de seguimiento adecuada:

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

Cuando una llamada de seguimiento recibe un objeto en el parámetro overrides, todos los valores válidos en el objeto override sobrescriben los valores en el objeto estándar de Analytics. Las variables ya definidas en el objeto de Analytics no se ven afectadas.
