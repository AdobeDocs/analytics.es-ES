---
description: La siguiente tabla muestra la diferencia entre el código correcto y los errores de código.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Errores de sintaxis comunes
topic: Developer and implementation
uuid: 9845dcb9-9f10-4f65-a43d-2af41edaa122
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Errores de sintaxis comunes

La siguiente tabla muestra la diferencia entre el código correcto y los errores de código.

| Incorrecto | Correcto |
|---|---|
| prop1 | s.prop1 (use "s.") |
| s.evar1 | s.eVar1 (usa mayúsculas y minúsculas correctas) |
| s.pagetype='errorpage'; | s.pageType='errorPage'; (usa mayúsculas y minúsculas correctas) |
| s.tl(this,o,pageA) | s.tl(this,'o','pageA'); (uso correcto de comillas simples) |
| s.events='event1'; s.events='event2'; | s.events='event1,event2'; (formato correcto) |
| s.pageName="John" (comillas tipográficas activadas) | s.pageName="John" (comillas tipográficas desactivadas) |
| s.products="shoes,UX4879,1,19.99" | s.products="shoes;UX4879;1;19.99" (usa punto y coma, no coma) |
| s.products=";MacBook Air;1;$1999.99" | s.products=";MacBook Air;1;1999.99" (no usa el signo de dólar) |
| s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183" | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95" (precios largos redondeados o truncados) |
| var s_account="rsid1, rsid2" | var s_account="rsid1,rsid2" (sin espacios entre las ID de grupo de informes cuando se etiquetan varios grupos) |
| s.events="event1, event2" | s.events="event1,event2" (sin espacios entre las ID de grupo de informes cuando se etiquetan varios grupos) |
| s.products="product name" | s.products=";product name" (usa punto y coma cuando no se incluyen categorías de productos en la lista) |

## Notas adicionales {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

Sitúe el comentario HTML de cierre muy al final del código Adobe (aunque use la parte NOSCRIPT del script).
