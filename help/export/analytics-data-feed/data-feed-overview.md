---
description: Los datos que se recopilan de sitios web y aplicaciones móviles, o que se cargan mediante las API del servicio web o fuentes de datos, se procesan y almacenan en el Data Warehouse de Adobe. Estos datos del flujo de navegación sin procesar forman el conjunto de datos que se utilizan en Adobe Analytics.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Resumen de la fuente de datos de Analytics
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 98%

---

# Resumen de la fuente de datos de Analytics

Las fuentes de datos son una forma eficaz de obtener datos sin procesar de Adobe Analytics. Estos datos sin procesar se pueden utilizar en otras plataformas fuera de Adobe para su uso según convenga a su organización. Los datos se entregan en lotes por hora al final de cada hora o en lotes diarios al final de cada día.

## Requisitos previos

Asegúrese de cumplir todos los requisitos antes de utilizar fuentes de datos.

* Tenga a mano un sitio FTP y credenciales. Las fuentes de datos solo se pueden enviar a un destino de servidor. Su organización suele proporcionar credenciales de FTP. Adobe puede proporcionar una ubicación FTP con una cantidad modesta de almacenamiento si así lo desea. Póngase en contacto con el Servicio de atención al cliente para solicitar un destino de FTP para fuentes de datos.
* Implementación de trabajo que envía datos a los servidores de recopilación de datos de Adobe. Consulte [Validación y publicación de una implementación en Launch](/help/implement/launch/validate-publish-prod.md) en la guía del usuario de implementación.
* Su cuenta es un administrador de productos de Analytics o pertenece a un perfil de producto con acceso a fuentes de datos.

## Pasos para empezar

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
   * Seleccione la última plantilla “Todas las columnas de Adobe” en el menú desplegable.
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

* [Crear una fuente de datos](create-feed.md): Detalles técnicos para crear una fuente de datos; explicación más detallada de los campos individuales
* [Administrar fuentes de datos](df-manage-feeds.md): Más información sobre cómo navegar por la interfaz de la fuente de datos
* [Contenido de la fuente de datos](c-df-contents/datafeeds-contents.md): Explicación sobre los elementos incluidos en un archivo comprimido
* [Definiciones de columnas de datos](c-df-contents/datafeeds-reference.md): Una lista completa de todas las columnas disponibles

## Recursos adicionales

Navegación de vídeo en la interfaz de fuente de datos:

>[!VIDEO](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/data-feeds/data-feeds-management-ui.html)
