---
title: Resumen general de las clasificaciones
description: Personalice la agrupación de los elementos de dimensión.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 25%

---

# Resumen general de las clasificaciones

Las clasificaciones permiten aplicar categorías a los datos de variables de Analytics para mostrarlos de distintos modos cuando se generan los informes. Se establece una relación entre un valor de variable y los metadatos relacionados con ese valor. Las clasificaciones se pueden utilizar en la mayoría de las dimensiones personalizadas, como el código de seguimiento, las props y las eVars.

El Adobe ofrece varias formas de clasificar los datos. Todos los datos de clasificación funcionan igual en los informes, y puede combinar cualquiera de estos métodos que se adapten mejor a su organización. Adobe recomienda utilizar **Conjuntos de clasificaciones**.

* **Conjuntos de clasificaciones**: cree y administre clasificaciones y sus reglas en una sola interfaz simplificada.
* **Reglas de clasificación**: Cree reglas que asignen un elemento de dimensión determinado a un elemento de dimensión de clasificación. Este método de clasificación de datos es mejor cuando una dimensión encuentra con frecuencia nuevos valores únicos o cuando la clasificación manual sería frecuente y engorrosa.
* **Importador de clasificaciones**: exporte una hoja de cálculo de plantilla con elementos de dimensión en cada fila. Las columnas representan cada clasificación de una dimensión. Este método de clasificación de datos es mejor cuando se conocen todos los elementos de dimensión y no requiere una actualización frecuente.

Una vez que una dimensión contiene datos de clasificación, se muestra una nueva dimensión en la creación de informes que solo contiene elementos de dimensión de clasificación. Por ejemplo, los [!UICONTROL ID de producto] pueden clasificarse con atributos de producto adicionales, como el nombre, el color, el tamaño, la descripción y la SKU del producto. Si se aumentan los datos de informes y análisis con atributos adicionales, podrán generarse informes más profundos y complejos.

Una sola dimensión puede tener varias dimensiones de clasificación. Por ejemplo, puede clasificar el código de seguimiento por motor de búsqueda, palabra clave y canal de campaña.

>[!VIDEO](https://video.tv.adobe.com/v/16853/?quality=12)
