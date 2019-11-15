---
description: La diferencia entre el modo activo y pasivo del FTP controla el modo en que se establecen las conexiones de puerto. Esta elección tiene efectos en el cortafuegos.
keywords: ftp;sftp
solution: Analytics
title: Uso del modo FTP pasivo
uuid: e56e937e-ec42-45ec-ae8e-8a8ea1b76f3f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Uso del modo FTP pasivo

La diferencia entre el modo activo y pasivo del FTP controla el modo en que se establecen las conexiones de puerto. Esta elección tiene efectos en el cortafuegos.

Adobe usa el FTP pasivo, una forma más segura de transferir datos en la que es el cliente del Programa de transferencia de archivos (FTP), y no el programa del servidor FTP, el que configura e inicia el flujo de datos. Si tiene problemas para conectarse al FTP de Adobe, asegúrese de estar usando el modo pasivo.
