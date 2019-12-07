---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# resolution

La variable indica la resolución de la pantalla del visitante que está viendo la página web.


<!-- 

resolution.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| s | WxH | 1680 x 1050 | Tráfico &gt; Tecnología &gt; Resolución del monitor |

