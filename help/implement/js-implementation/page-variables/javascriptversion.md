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



# javascriptVersion

La variable indica la versión de JavaScript que admite el explorador.


<!-- 

javascriptVersion.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Tráfico &gt; Tecnología &gt; Versión de JavaScript |

La versión H.10 y posteriores del archivo JavaScript detectan de forma precisa hasta la versión 1.7 (la última versión cuando se lanzó H.10). Las versiones anteriores del archivo JavaScript solo detectan hasta la versión 1.3
