---
title: Resumen general de las clasificaciones
description: Personalice la agrupación de los elementos de dimensión.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
TQID: https://experienceleague.adobe.com/raB90u-JEBgDroQPLC1eCSmxs4V-J7Av8Snr6oeKwvk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 84%

---

# Resumen general de las clasificaciones

Las clasificaciones permiten aplicar categorías a los datos de variables de Analytics para mostrarlos de distintos modos cuando se generan los informes. Establece una relación entre un valor variable y los metadatos relacionados con ese valor. Las clasificaciones se pueden utilizar en la mayoría de las dimensiones personalizadas, como [código de seguimiento](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) y [eVars](/help/components/dimensions/evar.md).

* **Los conjuntos de clasificación** son los componentes principales para clasificar los datos. [Los conjuntos de clasificación](/help/components/classifications/sets/overview.md) le permiten crear y gestionar clasificaciones en una interfaz única y simplificada.

* **Clasificaciones heredadas** documenta los métodos de clasificación heredados para clasificar datos. Estos métodos quedarán obsoletos en un futuro próximo y ya no se podrá acceder a ellos.

   * [Reglas de clasificación](/help/components/classifications/crb/classification-rule-builder.md): cree reglas que asignen un elemento de dimensión dado a un elemento de dimensión de clasificación. Este método para clasificar los datos es el mejor cuando una dimensión encuentra con frecuencia nuevos valores únicos o cuando la clasificación manual podría ser frecuente y engorrosa. Esta funcionalidad quedará obsoleta a partir del 28 de febrero de 2027.

   * [Importador de clasificaciones](/help/components/classifications/importer/c-working-with-saint.md): exporte una plantilla de hoja de cálculo con elementos de dimensión en cada fila. Las columnas representan cada clasificación de una dimensión. Este método para clasificar los datos es mejor cuando se conocen todos los elementos de la dimensión y no requiere una actualización frecuente. Esta funcionalidad quedará obsoleta a partir del 31 de agosto de 2026. Cuando quede obsoleto, ya no podrá importar clasificaciones mediante el FTP estándar.

Una misma dimensión puede tener varias dimensiones de clasificación. Por ejemplo, los [!UICONTROL ID de producto] pueden clasificarse con atributos de producto adicionales, como el nombre, el color, el tamaño, la descripción y la SKU del producto. Cada uno de estos atributos sería una dimensión de clasificación independiente perteneciente a la misma dimensión principal. Si se aumentan los informes con estos atributos, las oportunidades de creación de informes serán más profundas y complejas. Una vez que una dimensión contiene datos de clasificación, la dimensión de clasificación está disponible en la creación de informes que solo contienen elementos de dimensión de clasificación. Cualquier elemento de dimensión principal que no contenga un valor de clasificación se agrupa en [No especificado](/help/technotes/unspecified.md)
