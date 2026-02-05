---
description: Aprenda a utilizar las fuentes de datos para obtener datos sin procesar de Adobe Analytics. Descubra los requisitos previos para utilizar fuentes de datos y qué hacer a continuación.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Información general sobre las fuentes de datos de Analytics
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# Resumen de la fuente de datos de Analytics

Las fuentes de datos son una forma eficaz de obtener datos sin procesar de Adobe Analytics. Estos datos sin procesar se pueden utilizar en otras plataformas fuera de Adobe para su uso según convenga a su organización. Los datos se entregan en lotes por hora al final de cada hora o en lotes diarios al final de cada día.

## Requisitos previos

Asegúrese de cumplir todos los requisitos antes de utilizar fuentes de datos.

* Implementación de trabajo que envía datos a los servidores de recopilación de datos de Adobe. Consulte [Validación y publicación de una implementación](/help/implement/launch/validate-publish-prod.md) en la guía de implementación.
* Su cuenta es un administrador de productos de Analytics o pertenece a un perfil de producto con acceso a fuentes de datos.
* Un contenedor configurado en Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS.
* (Heredado: solo es necesario para tipos de destino FTP y SFTP heredados) Tenga a mano un sitio FTP y credenciales (credenciales de FTP proporcionadas por su organización).

## Pasos siguientes

Los siguientes recursos le ayudan a comprender el flujo de trabajo básico de la obtención de fuentes de datos. Después de comprender el flujo de trabajo básico, puede trabajar con equipos de su organización para almacenar o introducir datos sin procesar en una base de datos.

* [Prácticas recomendadas para fuentes de datos](/help/export/analytics-data-feed/data-feeds-best-practices.md): prácticas recomendadas para crear y administrar fuentes de datos.
* [Crear una fuente de datos](create-feed.md): Detalles técnicos para crear una fuente de datos; explicación más detallada de los campos individuales
* [Administrar fuentes de datos](df-manage-feeds.md): Más información sobre cómo navegar por la interfaz de la fuente de datos
* [Contenido de la fuente de datos](c-df-contents/datafeeds-contents.md): Comprender los elementos incluidos en un archivo <!-- Is this still the output users can download from the destination? I aske Jun. --> comprimido
* [Definiciones de columnas de datos](c-df-contents/datafeeds-reference.md): una lista completa de todas las columnas disponibles.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navegar por la interfaz de la fuente de datos](https://video.tv.adobe.com/v/3428561?captions=spa&quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Buscar su ID de fuente de datos](https://video.tv.adobe.com/v/3418479?captions=spa&quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]
