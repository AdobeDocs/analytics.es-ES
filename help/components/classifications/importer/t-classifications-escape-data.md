---
description: Pasos que describen cómo aplicar secuencias de escape a los datos de clasificación del archivo de clasificación.
title: Aplicar secuencias de escape a los datos de clasificación
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '104'
ht-degree: 100%

---

# Aplicar secuencias de escape a los datos de clasificación

Pasos que describen cómo aplicar secuencias de escape a los datos de clasificación del archivo de clasificación.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Compruebe que el formato del archivo de clasificación sea v2.1.

   Si v2.1 está habilitado, verá una línea similar a:

   >[!NOTE]
   >
   >Para especificar un formato de v2.1, habilite **[!UICONTROL Salida citada]** al exportar el archivo en la página [!UICONTROL Importador de clasificaciones] ([!UICONTROL Exportación del explorador] o [!UICONTROL Exportación FTP]).

1. Rodee el campo que contiene caracteres especiales con comillas dobles (`"`).

Puede aparecer un carácter de comillas dobles en una celda con caracteres de escape si se sustituye por dos caracteres de comillas dobles (`" "`). Por ejemplo:

```
My String "of data"
```

Con caracteres de escape, sería así:

```
"My String ""of data"""
```
