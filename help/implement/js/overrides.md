---
title: Anulaciones de variables
description: Las anulaciones de variables permiten cambiar el valor de una variable para un único seguimiento o una sola llamada de seguimiento de vínculos.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
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
