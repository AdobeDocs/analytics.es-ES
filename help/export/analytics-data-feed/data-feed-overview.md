---
description: Los datos que se recopilan de sitios web y aplicaciones móviles, o que se cargan mediante las API del servicio web o fuentes de datos, se procesan y almacenan en el Data Warehouse de Adobe. Estos datos del flujo de navegación sin procesar forman el conjunto de datos que se utilizan en Adobe Analytics.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Resumen de la fuente de datos de Analytics
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 0916ef4ddc2ca65f01721f4d79d7af825dcf50e3
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 83%

---

# Resumen de la fuente de datos de Analytics

>[!AVAILABILITY]
>
>Algunos de los tipos de destino descritos en esta página se encuentran en la fase de prueba limitada de la versión y es posible que aún no estén disponibles en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).

Las fuentes de datos son una forma eficaz de obtener datos sin procesar de Adobe Analytics. Estos datos sin procesar se pueden utilizar en otras plataformas fuera de Adobe para su uso según convenga a su organización. Los datos se entregan en lotes por hora al final de cada hora o en lotes diarios al final de cada día.

## Requisitos previos

Asegúrese de cumplir todos los requisitos antes de utilizar fuentes de datos.

* Implementación de trabajo que envía datos a los servidores de recopilación de datos de Adobe. Consulte [Validación y publicación de una implementación](/help/implement/launch/validate-publish-prod.md) en la Guía de implementación.
* Su cuenta es un administrador de productos de Analytics o pertenece a un perfil de producto con acceso a fuentes de datos.
* Un contenedor configurado en Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS.
* (Heredado: requerido solo para tipos de destino FTP y SFTP heredados) Tenga a mano un sitio FTP y credenciales (credenciales de FTP proporcionadas por su organización).

## Recursos de fuentes de datos recomendados

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
3. En la barra de navegación superior, vaya a Administración > Fuentes de datos.
4. Haga clic en [!UICONTROL Agregar]. Aparece una nueva página con tres categorías principales: [!UICONTROL Información de fuente], [!UICONTROL Destino] y [!UICONTROL Definiciones de columnas de datos].
5. Rellene los campos de [!UICONTROL Información de fuente].
   * Nombre: cualquier nombre que desee, como “Prueba de fuente de datos”.
   * Grupo de informes: seleccione el grupo de informes que desee.
   * Enviar un mensaje de correo electrónico cuando se complete: escriba su correo electrónico.
   * Intervalo de fuente: seleccione el intervalo deseado (por hora o por día).
   * Retrasar procesamiento: se puede dejar como [!UICONTROL Sin retraso].
   * Fechas de inicio y finalización: seleccione una fecha de inicio de varios días atrás y hoy como fecha de finalización.
6. Rellene los campos de [!UICONTROL Destino].
   * Tipo: FTP.
   * Host: introduzca la dirección URL de destino de FTP que desee. Por ejemplo: `ftp://ftp.omniture.com`.
   * Ruta: se puede dejar en blanco
   * Nombre de usuario: introduzca el nombre de usuario para iniciar sesión en el sitio FTP.
   * Contraseña y confirmar contraseña: introduzca la contraseña para iniciar sesión en el sitio FTP.
7. Complete las [!UICONTROL definiciones de columnas de datos].
   * Seleccione la última plantilla &quot;Todos los Adobe Columns&quot; en la lista desplegable.
   * Formato de compresión: Gzip.
   * Tipo de paquete: varios archivos.
   * Manifiesto: sin archivo.
8. Haga clic en [!UICONTROL Guardar] en la parte superior derecha.
9. Una vez guardado, comienza el procesamiento de datos históricos. Cuando los datos terminan de procesarse durante un día, el archivo se coloca en el sitio FTP.
10. Inicie sesión en el sitio FTP mediante el Explorador de Windows o un cliente FTP dedicado.
11. Descargue el archivo de fuente de datos comprimido en el equipo local.
12. Descomprima el archivo comprimido con un programa que admita extensiones de archivo `.tar.gz`.
13. Abra el archivo `hit_data.tsv` en la hoja de cálculo o la aplicación de base de datos que desee para ver los datos sin procesar de ese día.

## Pasos siguientes

Una vez que haya comprendido el flujo de trabajo básico de la obtención de fuentes de datos, puede trabajar con equipos de su organización para almacenar o introducir datos sin procesar en una base de datos.

* [Prácticas recomendadas de fuentes de datos](/help/export/analytics-data-feed/data-feeds-best-practices.md): Prácticas recomendadas para crear y administrar fuentes de datos.
* [Crear una fuente de datos](create-feed.md): Detalles técnicos para crear una fuente de datos; explicación más detallada de los campos individuales
* [Administrar fuentes de datos](df-manage-feeds.md): Más información sobre cómo navegar por la interfaz de la fuente de datos
* [Contenido de la fuente de datos](c-df-contents/datafeeds-contents.md): Explicación sobre los elementos incluidos en un archivo comprimido <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Definiciones de columnas de datos](c-df-contents/datafeeds-reference.md): Una lista completa de todas las columnas disponibles.
* Navegación de vídeo en la interfaz de fuente de datos:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Vídeo sobre cómo encontrar su ID de fuente de datos:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)