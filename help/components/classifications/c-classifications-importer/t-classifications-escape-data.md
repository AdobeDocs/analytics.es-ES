---
description: Pasos que describen cómo aplicar secuencias de escape a los datos de clasificación del archivo de clasificación.
subtopic: Classifications
title: Aplicar secuencias de escape a los datos de clasificación
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
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
