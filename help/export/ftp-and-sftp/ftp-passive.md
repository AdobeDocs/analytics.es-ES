---
description: La diferencia entre el modo activo y pasivo del FTP controla el modo en que se establecen las conexiones de puerto. Esta elección tiene efectos en el cortafuegos.
keywords: ftp;sftp
title: Uso del modo FTP pasivo
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '101'
ht-degree: 100%

---

# Uso del modo FTP pasivo

La diferencia entre el modo activo y pasivo del FTP controla el modo en que se establecen las conexiones de puerto. Esta elección tiene efectos en el cortafuegos.

Adobe usa el FTP pasivo, una forma más segura de transferir datos en la que es el cliente del Programa de transferencia de archivos (FTP), y no el programa del servidor FTP, el que configura e inicia el flujo de datos. Si tiene problemas para conectarse al FTP de Adobe, asegúrese de estar usando el modo pasivo.
