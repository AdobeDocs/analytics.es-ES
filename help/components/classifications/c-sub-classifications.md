---
description: Adobe Analytics admiten los modelos de clasificaciones de un solo nivel y de varios niveles. Las jerarquías de clasificación permiten aplicar una clasificación a otra.
subtopic: Classifications
title: Acerca de las subclasificaciones
topic: Admin tools
uuid: 48bd7fc1-54a1-40ef-bc55-395338522f2d
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 100%

---


# Acerca de las subclasificaciones

Adobe Analytics admite los modelos de clasificaciones de un solo nivel y de varios niveles. Las jerarquías de clasificación permiten aplicar una clasificación a otra.

>[!NOTE]
>
>Subclasificación hace referencia a la posibilidad de crear clasificaciones de clasificaciones. Sin embargo, no es lo mismo que la [!UICONTROL Jerarquía de clasificaciones] utilizada para crear informes de [!UICONTROL Jerarquía]. Para obtener más información sobre las jerarquías de clasificación, consulte [Jerarquías de clasificación](classification-hierarchies.md).

Por ejemplo:

![](assets/single-level-popup-C.png)

Cada clasificación de este modelo es independiente y corresponde a un nuevo subinforme de la variable de informe seleccionada. Además, cada clasificación constituye una columna de datos en el archivo de datos, con el nombre de la clasificación como encabezado de la columna. Por ejemplo:

| CLAVE | PROPIEDAD 1 | PROPIEDAD 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

Para obtener más información sobre el archivo de datos, consulte  [Archivos de datos de clasificación](/help/components/classifications/importer/c-saint-data-files.md).

Las clasificaciones de múltiples niveles están formadas por clasificaciones principales y secundarias. Por ejemplo:

![](assets/Multi-Level-Class-popup.png)

**Clasificaciones principales:** una clasificación principal es toda clasificación que tenga asociada una clasificación secundaria. Una clasificación puede ser clasificación principal y secundaria a la vez. Las clasificaciones principales de nivel superior corresponden a clasificaciones de un solo nivel (Consulte  [Clasificaciones de un solo nivel](/help/components/classifications/c-sub-classifications.md)).

**Clasificaciones secundarias:** una clasificación secundaria es toda clasificación que tenga otra clasificación como su principal en lugar de la variable. Las clasificaciones secundarias ofrecen información adicional sobre su clasificación principal. Por ejemplo, la clasificación [!UICONTROL Campañas] puede tener una clasificación secundaria de Propietario de la campaña. Las clasificaciones [!UICONTROL numéricas] también funcionan como métricas en los informes de clasificación.

Cada clasificación, ya sea principal o secundaria, constituye una columna de datos en el archivo de datos. Encabezamiento de columna de una clasificación secundaria utilizando el siguiente formato de convención de nombres:

`<parent_name>^<child_name>`

Para obtener más información sobre el formato del archivo de datos, consulte [Archivos de datos de clasificación](/help/components/classifications/importer/c-saint-data-files.md).

Por ejemplo:

| CLAVE | PROPIEDAD 1 | Propiedad 1&amp;Hat;Propiedad 1-1 | Propiedad 1&amp;Hat;Propiedad 1-2 | Propiedad 2 |
|---|---|---|---|---|
| 123 | ABC | Verde | Pequeño | A12B |
| 456 | DEF | Rojo | Grande | C3D4 |

Aunque la plantilla del archivo de una clasificación de múltiples niveles sea más compleja, el poder de estas clasificaciones es que los distintos niveles se pueden cargar como archivos por separado. Esta metodología puede utilizarse para reducir la cantidad de datos que deben cargarse periódicamente (diariamente, semanalmente, etc.) agrupando los datos en niveles de clasificación que cambian con el paso del tiempo en oposición a aquellos que no cambian.

>[!NOTE]
>
>Si la columna [!UICONTROL Clave] de un archivo de datos está en blanco, Adobe generará automáticamente claves únicas para cada fila de datos. Para evitar que se dañe el archivo al cargar un archivo de datos con datos de clasificación de segundo nivel o de nivel superior, rellene cada fila de la columna [!UICONTROL Clave] con un asterisco (*).

Consulte [Problemas comunes de carga de clasificaciones](https://helpx.adobe.com/es/analytics/kb/common-saint-upload-issues.html) para obtener ayuda sobre la resolución de problemas.

## Ejemplos

![](assets/sample-product-classifications.png)

>[!NOTE]
 Los datos de clasificación del producto están limitados a atributos de datos relacionados directamente con el producto (no se limitan en función de cómo se aplican categorías a los productos ni de cómo se venden en el sitio web). Los elementos de datos (como las categorías de venta, los nodos del explorador del sitio o los artículos de venta) no se consideran datos de clasificación del producto. Estos elementos se capturan en las variables de conversión de los informes.

Al cargar los archivos de datos correspondientes a esta clasificación de productos, puede cargar los datos de clasificación como un solo archivo o como varios archivos (ver más adelante). Si se separan el código de color en el archivo 1 y el nombre del color en el archivo 2, los datos del nombre del color (que ocupan pocas filas) solo deberán actualizarse cuando se creen nuevos códigos de color. Esto elimina el campo del nombre del color (CODE&amp;Hat;COLOR) del archivo 1, que se ha actualizado con mayor frecuencia, y por lo tanto reduce el tamaño del archivo y la complejidad al generar el archivo de datos.

### Clasificación del producto - Un archivo {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| CLAVE | NOMBRE DEL PRODUCTO | DETALLES DEL PRODUCTO | SEXO | TAMAÑO | CÓDIGO | CODE&amp;Hat;COLOR |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | Polo para hombre, Manga corta (M, 01) | M | M | 01 | Piedra |
| 410390014 | Polo-SS | Polo para hombre, Manga corta (L, 03) | M | L | 03 | Jaspeado |
| 410390015 | Polo-LS | Polo para mujer, Manga larga (S,23) | F | S | 23 | Agua |

### Clasificación del producto - Múltiples archivos (Archivo 1)  {#section_A99F7D0F145540069BA4EEC0597FF13F}

| CLAVE | NOMBRE DEL PRODUCTO | DETALLES DEL PRODUCTO | SEXO | TAMAÑO | CÓDIGO |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | Polo para hombre, Manga corta (M, 01) | M | M | 01 |
| 410390014 | Polo-SS | Polo para hombre, Manga corta (L, 03) | M | L | 03 |
| 410390015 | Polo-LS | Polo para mujer, Manga larga (S,23) | F | S | 23 |

### Clasificación del producto - Múltiples archivos (Archivo 2)  {#section_19ED95C33B174A9687E81714568D56A3}

| CLAVE | CÓDIGO | CODE&amp;Hat;COLOR |
|---|---|---|
| * | 01 | Piedra |
| * | 03 | Jaspeado |
| * | 23 | Agua |
