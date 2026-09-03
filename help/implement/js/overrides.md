---
title: Anulaciones de variables
description: Las anulaciones de variables permiten cambiar el valor de una variable para un único seguimiento o una sola llamada de seguimiento de vínculos.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
TQID: 'https://experienceleague.adobe.com/IVA-JMaZPrKpF1NhhL6o3uiCQOOCtZerk78aQTqJAyc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 106
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
