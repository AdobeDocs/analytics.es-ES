---
title: Preguntas más frecuentes sobre las clasificaciones
description: Preguntas más frecuentes sobre el uso de las clasificaciones.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Preguntas más frecuentes sobre las clasificaciones

Preguntas más frecuentes sobre el uso de las clasificaciones.

## ¿Cómo clasifico el elemento de dimensión &quot;0&quot;?

Los archivos de clasificación cargados con un valor clave o un valor de clasificación de cero (`0`) dan como resultado un error. Incluye todos los valores que solo contienen ceros (`00`, `000`, etc.). Existen varios métodos para resolver este problema:

* **Implementar valores** alternativos: El uso de un valor de texto distinto de `"0"` es la mejor y más sencilla forma de resolver este problema. Por ejemplo, cambie `s.campaign = "0";` la implementación a `s.campaign = "Zero";`.

* **Usar reglas** de procesamiento: Puede modificar los elementos de dimensión entre la recopilación de datos y su almacenamiento en un grupo de informes. Cree la siguiente regla de procesamiento:

   *Si[la dimensión]es igual a`0`, sobrescriba el valor de la[dimensión]con el valor personalizado`Zero`.*

* **Solicitar una regla** de VISTA: Un consultor de servicios de ingeniería configura una regla del lado del servidor por usted con un costo adicional. Póngase en contacto con el administrador de cuentas de su organización para solicitar una regla de VISTA.

## ¿Puedo usar el cargador para clasificar los elementos de dimensión que aún no existen?

Sí, *sin embargo, al hacerlo se cuenta cada elemento de dimensión como una llamada al servidor facturable.*

* Los artículos de Dimension que ya existen no incurren en ningún costo adicional.
* El uso del generador de reglas de clasificación no clasifica elementos inexistentes y, por lo tanto, no incurre en ningún costo adicional.
