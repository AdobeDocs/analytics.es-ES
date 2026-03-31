---
title: Resumen general de las clasificaciones
description: Personalice la agrupación de los elementos de dimensión.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 2e07f1b9495801383b030b2396e5468c39299f50
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 71%

---

# Resumen general de las clasificaciones

Las clasificaciones permiten aplicar categorías a los datos de variables de Analytics para mostrarlos de distintos modos cuando se generan los informes. Establece una relación entre un valor variable y los metadatos relacionados con ese valor. Las clasificaciones se pueden utilizar en la mayoría de las dimensiones personalizadas, como [código de seguimiento](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) y [eVars](/help/components/dimensions/evar.md).

* **Los conjuntos de clasificación** son los componentes principales para clasificar los datos. [Los conjuntos de clasificación](/help/components/classifications/sets/overview.md) le permiten crear y gestionar clasificaciones en una interfaz única y simplificada.

* **Clasificaciones heredadas** documenta los métodos de clasificación heredados para clasificar datos. Estos métodos quedarán obsoletos en un futuro próximo y ya no se podrá acceder a ellos.

   * [Reglas de clasificación](/help/components/classifications/crb/classification-rule-builder.md): cree reglas que asignen un elemento de dimensión dado a un elemento de dimensión de clasificación. Este método de clasificación de datos es mejor cuando una dimensión encuentra con frecuencia nuevos valores únicos o cuando las clasificaciones manuales serían frecuentes y engorrosas. Esta funcionalidad quedará obsoleta a partir del 28 de febrero de 2027.

   * [Importador de clasificaciones](/help/components/classifications/importer/c-working-with-saint.md): exporte una plantilla de hoja de cálculo con elementos de dimensión en cada fila. Las columnas representan cada clasificación de una dimensión. Este método de clasificación de datos es mejor cuando se conocen todos los elementos de dimensión y no requiere una actualización frecuente. Esta funcionalidad quedará obsoleta a partir del 31 de agosto de 2026. Cuando quede obsoleto, ya no podrá importar clasificaciones mediante el FTP estándar.

Una misma dimensión puede tener varias dimensiones de clasificación. Por ejemplo, los [!UICONTROL ID de producto] pueden clasificarse con atributos de producto adicionales, como el nombre, el color, el tamaño, la descripción y la SKU del producto. Cada uno de estos atributos sería una dimensión de clasificación independiente perteneciente a la misma dimensión principal. Si se aumentan los informes con estos atributos, las oportunidades de creación de informes serán más profundas y complejas. Una vez que una dimensión contiene datos de clasificación, la dimensión de clasificación está disponible en la creación de informes que solo contienen elementos de dimensión de clasificación. Cualquier elemento de dimensión principal que no contenga un valor de clasificación se agrupa en [No especificado](/help/technotes/unspecified.md)
