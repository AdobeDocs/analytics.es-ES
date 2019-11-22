---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# colorDepth

La variable se utiliza para mostrar el número de bits usado para mostrar el color en cada píxel de la pantalla.


<!-- 

colordepth.xml

 -->

Por ejemplo, 32 representa 32 bits de color en la pantalla. Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en `props/eVars`, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| c | 8, 16 y 32 | 32 | Tráfico &gt; Tecnología &gt; Profundidad de color del monitor |
