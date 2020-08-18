---
title: Archivo de registro
description: Obtenga un archivo de registro para solucionar problemas.
translation-type: tm+mt
source-git-commit: aea3b4448b61e8b1b217b4f74b0b80c9fbedd070
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# Archivo de registro

Al solucionar problemas con Ad Hoc Analysis, a veces es necesario obtener su archivo de registro. Adobe puede utilizar el archivo de registro para localizar la causa raíz del problema y proporcionar una resolución. El `discover.log` archivo contiene todas las interacciones del usuario, información de carga de informes y mensajes de error de Java en todas las sesiones. Activa cualquier información protegida, como la contraseña del usuario. Los archivos de registro grandes se dividen en incrementos de 10 MB. Al proporcionar Adobe con los archivos de registro, asegúrese de que todos los archivos están seleccionados.

## Windows

Obtenga el `discover.log` archivo para Windows:

1. Haga clic en el menú inicio y seleccione **Ejecutar** o pulse `[Win]` + `[R]`.
2. Pegue lo siguiente en el campo de texto y haga clic en **Aceptar**:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. Resalte todos los archivos de la carpeta, haga clic con el botón derecho y elija **Enviar a > Carpeta** comprimida (comprimida).
4. Proporcione al representante de Adobe el archivo .zip.

## Mac

Para obtener el `discover.log` archivo para Mac OS, haga lo siguiente:

1. Abra el Buscador y navegue hasta `/Users/your-user/.adobe/Discover/log`
2. Resalte todos los archivos de la carpeta, haga clic con el botón derecho y elija **Comprimir**.
3. Proporcione al representante de Adobe el archivo .zip.

Si el tamaño total de un archivo comprimido supera los 10 MB, un representante de Adobe puede proporcionar una ubicación FTP temporal.
