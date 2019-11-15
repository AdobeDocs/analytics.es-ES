---
description: Es posible volver a ejecutar uno o varios trabajos de la lista Trabajos.
keywords: Data Feed;job;rerun
solution: Analytics
title: Volver a ejecutar un trabajo
uuid: 5caf95da-dd88-4b1a-a081-684f4fd1f714
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

