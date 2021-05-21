---
description: Si se produce un error, se notifica en la columna Estado del trabajo.
keywords: Fuente de datos;trabajo;resolución de problemas;error;ftp;chdir;conexión;inicio de sesión;put
title: Solución de problemas de los trabajos
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
exl-id: c082bc95-cdae-448b-86b5-695660fb2352
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '464'
ht-degree: 100%

---

# Solución de problemas de los trabajos

Si tiene problemas para que una fuente de datos aparezca en su sitio FTP, utilice esta página para comprender por qué ocurre esto.

## Códigos de error

Si se produce un error, se notifica en la columna Estado del trabajo.

### Error Chdir de FTP

La fuente no puede desplazarse ni escribir en la carpeta especificada. Asegúrese de que la carpeta de destino exista en el sitio FTP y de que las credenciales proporcionadas tengan los permisos de lectura y escritura correctos para esa carpeta.

### Error de conexión al FTP

La fuente no se puede conectar al destino de FTP. Compruebe que el destino FTP sea correcto y válido.

### Error de FTP

Error genérico en el que la fuente no puede escribir el archivo en el sitio FTP. Este error podría deberse a que el disco del servidor FTP esté lleno o a que se haya superado la cuota. El problema también se puede originar a partir de un error de red o de servidor de destino.

### Error de inicio de sesión en el FTP

La fuente no puede iniciar sesión con las credenciales proporcionadas. Compruebe que el nombre de usuario y la contraseña de FTP son correctos.

### Error Put de FTP

La fuente no puede escribir archivos en el sitio FTP. Compruebe que el inicio de sesión en FTP tiene los permisos correctos para leer y escribir datos en su sitio FTP. Este error también puede producirse potencialmente por un disco que esté completo o una cuota de disco que se haya excedido en el servidor FTP.

## Pasos para solucionar los problemas

Inicie sesión en el sitio FTP y suba cualquier archivo. En la mayoría de los casos, puede determinar el punto del error mediante estos pasos.

1. Inicie sesión en el sitio FTP mediante el Explorador de archivos (Windows) o el Finder (Mac). Compruebe que utiliza el protocolo FTP (`ftp://`). Si no puede acceder al sitio FTP, trabaje con el propietario del sitio FTP para determinar el destino correcto.

   ![Explorador de archivos](assets/file_explorer.png)

2. Aparece una ventana emergente que solicita un nombre de usuario y una contraseña. Introduzca sus credenciales de autenticación. Si se aceptan las credenciales, la ventana muestra el contenido actual en el sitio FTP. Si no se aceptan las credenciales, puede trabajar con el propietario del FTP para asegurarse de que el nombre de usuario y la contraseña son correctos.
3. Suba un archivo al sitio FTP arrastrándolo hasta la ventana autenticada. Cualquier imagen o documento de texto es adecuado. Si aparece un error al intentar colocar un archivo en el sitio FTP, trabaje con el propietario del FTP para comprobar que hay suficiente espacio en disco y que el nombre de usuario tiene permisos de escritura.
4. Una vez que haya confirmado que el archivo se encuentra en el sitio FTP, puede eliminar el archivo que ha subido en el paso anterior.
5. Si todos los pasos anteriores funcionan y sigue experimentando un error de FTP, pida a un representante de asistencia al cliente que contacte con el Servicio de atención al cliente.
