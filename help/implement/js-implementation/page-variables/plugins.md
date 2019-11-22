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


# plugins

La variable, en exploradores Netscape y Mozilla, enumera los complementos instalados en el explorador.


<!-- 

plugins.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| p | Complementos reconocidos | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Biblioteca de vínculos dinámicos del complemento Reproductor de Windows Media;Microsoft® DRM; | Tráfico &gt; Tecnología &gt; Complementos |
