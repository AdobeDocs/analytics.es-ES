---
description: Adobe Analytics admiten los modelos de clasificaciones de un solo nivel y de varios niveles. Las jerarquías de clasificación permiten aplicar una clasificación a otra.
subtopic: Classifications
title: Acerca de las subclasificaciones
topic: Admin tools
uuid: 48bd7fc1-54a1-40ef-bc55-395338522f2d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Acerca de las subclasificaciones

Adobe Analytics admite modelos de clasificaciones de un solo nivel y de varios niveles. Las jerarquías de clasificación permiten aplicar una clasificación a otra.

>[!NOTE] Subclasificación hace referencia a la posibilidad de crear clasificaciones de clasificaciones. However, this is not the same as a [!UICONTROL Classification Hierarchy] used to create [!UICONTROL Hierarchy] reports. Para obtener más información sobre las jerarquías de clasificación, consulte [Jerarquías de clasificación](classification-hierarchies.md).

Por ejemplo:

![](assets/single-level-popup-C.png)

Cada clasificación de este modelo es independiente y corresponde a un nuevo subinforme para la variable de sistema de informes seleccionada. Además, cada clasificación constituye una columna de datos en el archivo de datos, con el nombre de la clasificación como encabezado de columna. Por ejemplo:

| CLAVE | PROPIEDAD 1 | PROPIEDAD 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

Para obtener más información sobre el archivo de datos, consulte  [Archivos de datos de clasificación](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

Las clasificaciones de múltiples niveles están compuestas de clasificaciones principales y secundarias. Por ejemplo:

![](assets/Multi-Level-Class-popup.png)

**Clasificaciones principales:** una clasificación principal es toda clasificación que tenga asociada una clasificación secundaria. Una clasificación puede ser clasificación principal y secundaria a la vez. Las clasificaciones principales de nivel superior corresponden a clasificaciones de un solo nivel (Consulte  [Clasificaciones de un solo nivel](/help/components/c-classifications2/c-sub-classifications.md)).

**Clasificaciones secundarias:** una clasificación secundaria es toda clasificación que tenga otra clasificación como su principal en lugar de la variable. Las clasificaciones secundarias proporcionan información adicional sobre su clasificación principal. Por ejemplo, una [!UICONTROL Campaigns] clasificación puede tener una clasificación secundaria Propietario de Campaña. [!UICONTROL Numeric] las clasificaciones también funcionan como métricas en los informes de clasificación.

Cada clasificación, ya sea principal o secundaria, constituye una columna de datos en el archivo de datos. El encabezado de columna de una clasificación secundaria con el siguiente formato de nombre:

`<parent_name>^<child_name>`

Para obtener más información sobre el formato del archivo de datos, consulte [Archivos de datos de clasificación](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

Por ejemplo:

| CLAVE | PROPIEDAD 1 | Propiedad 1&amp;Hat;Propiedad 1-1 | Propiedad 1&amp;Hat;Propiedad 1-2 | Propiedad 2 |
|---|---|---|---|---|
| 123 | ABC | Verde | Pequeño | A12B |
| 456 | DEF | Rojo | Grande | C3D4 |

Aunque la plantilla de archivo para una clasificación multinivel es más compleja, el poder de las clasificaciones multinivel es que los niveles independientes se pueden cargar como archivos separados. Este método se puede utilizar para minimizar la cantidad de datos que se deben cargar periódicamente (diariamente, semanalmente, etc.) agrupando los datos en niveles de clasificación que cambian con el tiempo en comparación con los que no.

>[!NOTE] Si la [!UICONTROL Key] columna de un archivo de datos está en blanco, Adobe genera automáticamente claves únicas para cada fila de datos. Para evitar posibles daños en los archivos al cargar un archivo de datos con datos de clasificación de segundo nivel o de nivel superior, rellene cada fila de la [!UICONTROL Key] columna con un asterisco (*).

Consulte [Problemas comunes de carga de clasificaciones](https://marketing.adobe.com/resources/help/es_ES/home/index.html#kb-common-saint-upload-issues) para obtener ayuda sobre la resolución de problemas.

## Ejemplos

![](assets/sample-product-classifications.png)

>[!NOTE] Los datos de clasificación del producto están limitados a atributos de datos relacionados directamente con el producto Los datos no se limitan a cómo se categorizan o venden los productos en el sitio web. Los elementos de datos como categorías de venta, nodos del explorador del sitio o artículos de venta no son datos de clasificación del producto. En su lugar, estos elementos se capturan en variables de conversión de informes.

Al cargar archivos de datos para esta clasificación de productos, puede cargar los datos de clasificación como un solo archivo o como varios archivos (véase más adelante). Al separar el código de color en el archivo 1 y el nombre del color en el archivo 2, los datos del nombre del color (que pueden ser sólo unas pocas filas) sólo deben actualizarse cuando se crean nuevos códigos de color. Esto elimina el campo del nombre del color (CODE&amp;Hat;COLOR) del archivo 1, que se ha actualizado con mayor frecuencia, y por lo tanto reduce el tamaño del archivo y la complejidad al generar el archivo de datos.

### Clasificación del producto - Un archivo {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| CLAVE | NOMBRE DEL PRODUCTO | DETALLES DEL PRODUCTO | SEXO | TAMAÑO | CÓDIGO | CODE&amp;Hat;COLOR |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | Polo para hombre, Manga corta (M,01) | L | L | 01 | Piedra |
| 410390014 | Polo-SS | Polo para hombre, Manga corta (L,03) | L | L | 03 | Heather |
| 410390015 | Polo-LS | Polo de mujer, Manga larga (S,23) | V | S | 23 | Aqua |

### Clasificación del producto - Múltiples archivos (Archivo 1)  {#section_A99F7D0F145540069BA4EEC0597FF13F}

| CLAVE | NOMBRE DEL PRODUCTO | DETALLES DEL PRODUCTO | SEXO | TAMAÑO | CÓDIGO |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | Polo para hombre, Manga corta (M,01) | L | L | 01 |
| 410390014 | Polo-SS | Polo para hombre, Manga corta (L,03) | L | L | 03 |
| 410390015 | Polo-LS | Polo de mujer, Manga larga (S,23) | V | S | 23 |

### Clasificación del producto - Múltiples archivos (Archivo 2)  {#section_19ED95C33B174A9687E81714568D56A3}

| CLAVE | CÓDIGO | CODE&amp;Hat;COLOR |
|---|---|---|
| * | 01 | Piedra |
| * | 03 | Heather |
| * | 23 | Aqua |
