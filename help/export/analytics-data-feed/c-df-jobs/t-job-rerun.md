---
description: Es posible volver a ejecutar uno o varios trabajos de la lista Trabajos.
keywords: Fuente de datos; trabajo; volver a ejecutar
seo-description: Es posible volver a ejecutar uno o varios trabajos de la lista Trabajos.
seo-title: Volver a ejecutar un trabajo
solution: Analytics
title: Volver a ejecutar un trabajo
uuid: 5 caf 95 da-dd 88-4 b 1 a-a 081-684 f 4 fd 1 f 714
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Volver a ejecutar un trabajo

Es posible volver a ejecutar uno o varios trabajos de la lista Trabajos.

1. Seleccione los trabajos que desee volver a ejecutar.
1. Click **[!UICONTROL Rerun Job]**.

   El proceso de ejecución depende del estado actual del trabajo:

   | Estado | Nombre de archivo en la caché del servidor | Proceso |
   |---|---|---|
   | Completado | Sí | El archivo se vuelve a enviar. |
   | Completado | No | El trabajo se vuelve a procesar y, a continuación, se envía de nuevo. |
   | Error | No | El trabajo se vuelve a procesar y, a continuación, se envía de nuevo. |
   | Otro estado | N/A | No compatible. |

