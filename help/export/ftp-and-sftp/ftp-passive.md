---
description: La diferencia entre el modo activo y pasivo del FTP controla el modo en que se establecen las conexiones de puerto. Esta elección tiene efectos en el cortafuegos.
keywords: ftp;sftp
title: Uso del modo FTP pasivo
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 85%

---

# Uso del modo FTP pasivo

La diferencia entre el modo activo y pasivo del FTP controla el modo en que se establecen las conexiones de puerto. Esta elección tiene efectos en el cortafuegos.

Adobe usa el FTP pasivo, una forma más segura de transferir datos en la que es el cliente del Programa de transferencia de archivos (FTP), y no el programa del servidor FTP, el que configura e inicia el flujo de datos. Si tiene dificultades para conectarse al FTP de Adobe, asegúrese de utilizar el modo pasivo.
