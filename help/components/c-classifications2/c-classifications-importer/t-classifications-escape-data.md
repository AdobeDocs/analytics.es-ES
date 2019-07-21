---
description: Pasos que describen cómo aplicar secuencias de escape a los datos de clasificación del archivo de clasificación.
seo-description: Pasos que describen cómo aplicar secuencias de escape a los datos de clasificación del archivo de clasificación.
seo-title: Aplicar secuencias de escape a los datos de clasificación
solution: Analytics
subtopic: Clasificaciones
title: Aplicar secuencias de escape a los datos de clasificación
topic: Herramientas de administración
uuid: 724 edcc 5-4990-4 f 24-afbb -9 aef 301791 a 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aplicar secuencias de escape a los datos de clasificación

Pasos que describen cómo aplicar secuencias de escape a los datos de clasificación del archivo de clasificación.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Compruebe que el formato del archivo de clasificación sea v2.1.

   Si v2.1 está habilitado, verá una línea similar a:

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Rodee el campo que contiene caracteres especiales con comillas dobles (`"`).

Puede aparecer un carácter de comillas dobles en una celda con caracteres de escape si se sustituye por dos caracteres de comillas dobles (`" "`). Por ejemplo:

```
My String "of data"
```

Con caracteres de escape, sería así:

```
"My String ""of data"""
```
