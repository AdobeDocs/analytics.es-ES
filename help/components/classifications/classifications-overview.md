---
title: Resumen general de las clasificaciones
description: Personalice la agrupación de los elementos de dimensión.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 3701aa7a2a1528cd735c70fc7b061755a15b34a6
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 36%

---

# Resumen general de las clasificaciones

Las clasificaciones permiten aplicar categorías a los datos de variables de Analytics para mostrarlos de distintos modos cuando se generan los informes. Establece una relación entre un valor variable y los metadatos relacionados con ese valor. Las clasificaciones se pueden usar en la mayoría de las dimensiones personalizadas, como [código de seguimiento](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) y [eVars](/help/components/dimensions/evar.md).

**Los conjuntos de clasificaciones** son la forma principal de clasificar los datos. **Reglas de clasificación** y **Importador de clasificaciones** son métodos heredados para clasificar datos. Estos métodos están obsoletos y ya no estarán accesibles a partir del 31 de agosto de 2026.

* **Conjuntos de clasificaciones**: cree y administre clasificaciones en una sola interfaz simplificada.
* **Reglas de clasificación** (heredadas): cree reglas que asignen un elemento de dimensión determinado a un elemento de dimensión de clasificación. Este método de clasificación de datos es mejor cuando una dimensión encuentra con frecuencia nuevos valores únicos o cuando las clasificaciones manuales serían frecuentes y engorrosas.
* **Importador de clasificaciones** (heredado): exporte una hoja de cálculo de plantilla con elementos de dimensión en cada fila. Las columnas representan cada clasificación de una dimensión. Este método para clasificar los datos es mejor cuando se conocen todos los elementos de la dimensión y no requiere una actualización frecuente.

Una misma dimensión puede tener varias dimensiones de clasificación. Por ejemplo, los [!UICONTROL ID de producto] pueden clasificarse con atributos de producto adicionales, como el nombre, el color, el tamaño, la descripción y la SKU del producto. Cada uno de estos atributos sería una dimensión de clasificación independiente que pertenecería a la misma dimensión principal. Si se aumentan los informes con estos atributos, las oportunidades de creación de informes serán más profundas y complejas. Una vez que una dimensión contiene datos de clasificación, la dimensión de clasificación está disponible en los informes que solo contienen elementos de dimensión de clasificación. Cualquier elemento de dimensión principal que no contenga un valor de clasificación se agrupa en [No especificado](/help/technotes/unspecified.md)
