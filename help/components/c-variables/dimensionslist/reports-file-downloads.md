---
description: Descargas de archivos ayuda a conocer la frecuencia con la que los visitantes descargan archivos del sitio. Entre los ejemplos de descargas de archivos se pueden citar documentos de procesadores de textos, hojas de cálculo, archivos de audio, archivos de vídeo, manuales de usuario, etc. Esto incluye tanto archivos que se hayan guardado y abierto directamente desde el explorador, como archivos guardados en el equipo del usuario. El informe muestra el nombre del archivo descargado y la dirección URL completa necesaria para acceder al archivo.
title: Descargas de archivos
topic: Reports
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Descargas de archivos

Descargas de archivos ayuda a conocer la frecuencia con la que los visitantes descargan archivos del sitio. Entre los ejemplos de descargas de archivos se pueden citar documentos de procesadores de textos, hojas de cálculo, archivos de audio, archivos de vídeo, manuales de usuario, etc. Esto incluye tanto archivos que se hayan guardado y abierto directamente desde el explorador, como archivos guardados en el equipo del usuario. El informe muestra el nombre del archivo descargado y la dirección URL completa necesaria para acceder al archivo.

**Navegación**

**[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Links]** > **[!UICONTROL File Downloads]**

Si este informe no está disponible en la ubicación predeterminada, consulte a sus administradores, que pueden haber cambiado la estructura de menú predeterminada para atender mejor a las necesidades específicas de la organización.

Utilice este informe para:

* Determinar cuáles son los archivos que se descargan con mayor frecuencia desde el sitio.
* Saber si algunos archivos se descargan con mayor frecuencia durante períodos de tiempo específicos.
* Confirmar que se requieran todos los formatos para un documento determinado.

   Por ejemplo: quizás traduce a doce idiomas diferentes los manuales del usuario y los pone a disposición de los usuarios en el sitio web. Con los informes de descarga de archivos, conocerá la frecuencia con la que se descarga cada una de las versiones de los manuales del usuario y podrá evaluar si vale la pena continuar con la traducción del manual a los doce idiomas.

**Resolución de problemas**

Los informes de marketing capturan información sobre los archivos descargados desde cualquier página del sitio que contenga código JavaScript. Sin embargo, es necesario que ciertas variables estén presentes y configuradas correctamente para que la información de descarga de archivos se pueda recoger en informes. Si este informe no muestra datos o no contiene los valores esperados, siga los pasos siguientes para validar su implementación.

1. En el sitio, busque el archivo de JavaScript global. Normalmente se denomina [!DNL s_code.js], pero es posible que se le haya cambiado el nombre. Si se le ha cambiado el nombre, puede buscar en los archivos JavaScript de su sitio el valor *`s.account`*, que forma parte del código JavaScript.

1. En el archivo, localice la variable [s.trackDownloadLinks](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/config-vars/trackdownloadlinks.translate.html). Asegúrese de que esté configurada en *true*.

1. Localice la variable [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/config-vars/linkdownloadfiletypes.translate.html). Asegúrese de que todas las extensiones de archivo deseadas estén presentes en la lista. En caso necesario, agregue las extensiones que faltan (por ejemplo, [!DNL .zip], [!DNL .pdf], etc.)

If these variables appear to be configured correctly, but the [!UICONTROL File Downloads Report] still is not receiving data, your organization&#39;s supported users should contact Customer Care.
