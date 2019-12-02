---
description: Los datos que se recopilan de sitios web y aplicaciones móviles, o que se cargan mediante las API del servicio web o fuentes de datos, se procesan y almacenan en el Data Warehouse de Adobe. Estos datos del flujo de navegación sin procesar forman el conjunto de datos que se utilizan en Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
solution: Analytics
title: Resumen de la fuente de datos de Analytics
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Resumen de la fuente de datos de Analytics

Las fuentes de datos son una forma eficaz de obtener datos sin procesar de Adobe Analytics. Estos datos sin procesar se pueden utilizar en otras plataformas fuera de Adobe para su uso a discreción de su organización. Los datos se entregan en lotes por hora al final de cada hora o en lotes diarios al final de cada día.

## Requisitos previos

Asegúrese de cumplir todos los requisitos siguientes antes de utilizar fuentes de datos.

* Tenga a mano un sitio FTP y credenciales. Las fuentes de datos solo se pueden enviar a un destino de servidor. Su organización suele proporcionar credenciales de FTP. Adobe puede proporcionar una ubicación FTP con una cantidad modesta de almacenamiento a petición suya. Póngase en contacto con el Servicio de atención al cliente para solicitar un destino de FTP para fuentes de datos.
* Implementación de trabajo que envía datos a los servidores de recopilación de datos de Adobe. Consulte [Validación y publicación de una implementación en Launch](../../implement/implement-with-launch/validate-publish-prod.md) en la guía de usuario Implementación.
* Su cuenta es un administrador de productos de Analytics o su cuenta pertenece a un perfil de producto con acceso a fuentes de datos.

## Pasos para empezar

1. Inicie sesión en [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
3. En la barra de navegación superior, vaya a Administración &gt; Fuentes de datos.
4. Haga clic en [!UICONTROL Agregar]. Aparece una nueva página con tres categorías principales: Información [!UICONTROL de]fuente, [!UICONTROL Destino]y Definiciones [!UICONTROL de columnas de datos].
5. Rellene los campos [!UICONTROL Información] de fuente.
   * Nombre: Cualquier nombre que desee, como "Probar fuente de datos".
   * Grupo de informes: Seleccione el grupo de informes que desee.
   * Enviar un mensaje de correo electrónico cuando se complete: Escriba su correo electrónico.
   * Intervalo de fuente: Seleccione el intervalo deseado (por hora o por día).
   * Retrasar procesamiento: Se puede dejar como [!UICONTROL Sin retraso].
   * Fechas de inicio y finalización: Seleccione una fecha de inicio desde hace varios días y hoy como fecha de finalización.
6. Rellene los campos [!UICONTROL Destino] .
   * Tipo: FTP
   * Host: Introduzca la dirección URL de destino de FTP que desee. Por ejemplo, `ftp://ftp.omniture.com`.
   * Ruta: Se puede dejar en blanco
   * Nombre de usuario: Introduzca el nombre de usuario para iniciar sesión en el sitio FTP.
   * Contraseña y confirmar contraseña: Introduzca la contraseña para iniciar sesión en el sitio FTP.
7. Complete las definiciones [!UICONTROL de columnas]de datos.
   * Seleccione la última plantilla 'Todas las columnas de Adobe' en el menú desplegable.
   * Formato de compresión: Gzip
   * Tipo de paquete: Varios archivos
   * Manifiesto: Sin archivo
8. Haga clic en [!UICONTROL Guardar] en la parte superior derecha.
9. Una vez guardado, comienza el procesamiento de datos históricos. Cuando los datos terminan de procesarse durante un día, el archivo se coloca en el sitio FTP.
10. Inicie sesión en el sitio FTP mediante el Explorador de Windows o un cliente FTP dedicado.
11. Descargue el archivo de fuente de datos comprimido en el equipo local.
12. Descomprima el archivo comprimido con un programa que admita extensiones `.tar.gz` de archivo.
13. Abra el `hit_data.tsv` archivo en la hoja de cálculo o la aplicación de base de datos que desee para ver los datos sin procesar de ese día.

## Pasos siguientes

Una vez que haya comprendido el flujo de trabajo básico de la obtención de fuentes de datos, puede trabajar con equipos de su organización para almacenar o ingestar datos sin procesar en una base de datos.

[Crear una fuente](create-feed.md)de datos: Detalles técnicos para crear una fuente de datos, que explican los campos individuales con más detalle[Administrar fuentes](df-manage-feeds.md)de datos: Obtenga más información sobre cómo navegar por el contenido[de fuentes](c-df-contents/datafeeds-contents.md)de datos en la interfaz de fuentes de datos: Comprenda qué hay dentro del archivo[comprimido Definiciones](c-df-contents/datafeeds-reference.md)de columnas de datos: Una lista completa de todas las columnas disponibles

## Recursos adicionales

Navegación de vídeo en la interfaz de fuente de datos:

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
