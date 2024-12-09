---
title: Resumen general de las clasificaciones
description: Personalice la agrupación de los elementos de dimensión.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 0f5890679ea73c1bbea9f5d2939e89c6775c85da
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 62%

---

# Resumen general de las clasificaciones

Las clasificaciones permiten aplicar categorías a los datos de variables de Analytics para mostrarlos de distintos modos cuando se generan los informes. Establece una relación entre un valor variable y los metadatos relacionados con ese valor. Las clasificaciones se pueden usar en la mayoría de las dimensiones personalizadas, como [código de seguimiento](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) y [eVars](/help/components/dimensions/evar.md).

Adobe ofrece múltiples formas de clasificar los datos. Todos los datos de clasificación funcionan igual en la creación de informes, y puede combinar cualquiera de estos métodos que mejor se adapte a su organización. Adobe recomienda utilizar **Conjuntos de clasificación**.

* **Conjuntos de clasificación**: cree y gestione clasificaciones y sus reglas en una interfaz única y simplificada.
* **Reglas de clasificación**: cree reglas que asignen un elemento de dimensión dado a un elemento de dimensión de clasificación. Este método de clasificación de datos es mejor cuando una dimensión encuentra con frecuencia nuevos valores únicos o cuando las clasificaciones manuales serían frecuentes y engorrosas.
* **Importador de clasificaciones**: exporte una plantilla de hoja de cálculo con elementos de dimensión en cada fila. Las columnas representan cada clasificación de una dimensión. Este método para clasificar los datos es mejor cuando se conocen todos los elementos de la dimensión y no requiere una actualización frecuente.

Una misma dimensión puede tener varias dimensiones de clasificación. Por ejemplo, los [!UICONTROL ID de producto] pueden clasificarse con atributos de producto adicionales, como el nombre, el color, el tamaño, la descripción y la SKU del producto. Cada uno de estos atributos sería una dimensión de clasificación independiente que pertenecería a la misma dimensión principal. Si se aumentan los informes con estos atributos, las oportunidades de creación de informes serán más profundas y complejas. Una vez que una dimensión contiene datos de clasificación, la dimensión de clasificación está disponible en los informes que solo contienen elementos de dimensión de clasificación. Cualquier elemento de dimensión principal que no contenga un valor de clasificación se agrupa en [No especificado](/help/technotes/unspecified.md)
