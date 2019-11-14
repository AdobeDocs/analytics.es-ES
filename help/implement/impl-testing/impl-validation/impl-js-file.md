---
description: Compruebe que la referencia al archivo .JS desde la página es correcta. Se puede especificar una ruta relativa al documento actual o se puede usar una ruta absoluta.
keywords: Analytics Implementation
solution: Analytics
title: Archivo JS de JavaScript
topic: Developer and implementation
uuid: 6e83223f-2127-41d3-9806-bd085fa2a747
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Archivo JS de JavaScript

Compruebe que la referencia al archivo .JS desde la página es correcta. Se puede especificar una ruta relativa al documento actual o se puede usar una ruta absoluta.

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

Si algunas páginas del sitio se cargan en un protocolo seguro (https:) y hacen referencia a [!DNL AppMeasurement] del archivo JavaScript, compruebe que la referencia al archivo sea segura (mediante https:) o codifique la referencia tal y como se indica a continuación. En este ejemplo se usa el protocolo de la página actual y evita la advertencia "algunos elementos no son seguros".

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Asegúrese de que el archivo [!DNL .JS] en los servidores web tenga correctamente configurados los permisos de manera que los visitantes del sitio web puedan descargar y ejecutar el archivo. Si se usa un archivo [!DNL .JS] diferente en los servidores de desarrollo, configure el atributo “solo lectura” para el archivo [!DNL .JS] en los servidores de producción para evitar sobrescribirlo. Si se modifica, asegúrese de que las siguientes opciones estén correctamente configuradas en la parte superior del archivo [!DNL .JS]:

```js
/************************** CONFIG SECTION **************************/
/* You may add or alter any code config here.                       */
/* Link Tracking Config */
s.trackDownloadLinks=false /* true for download tracking */
s.trackExternalLinks=false /* true for exit link tracking */
s.trackInlineStats=false /* true for ClickMap support */
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls"
s.linkInternalFilters="javascript:"
s.linkLeaveQueryString=false
s.linkTrackVars="None" 
s.linkTrackEvents="None"
```

Si “*`s_account`*” tiene asignado un valor en la parte superior del archivo [!DNL .JS], asegúrese de que el ID del grupo de informes (que se rellena en la variable [!UICONTROL s_account]) sea correcto. Asegúrese también de que el código de la página no esté configurando el [!UICONTROL ID de grupo de informes] (variable *`s_account`*).

Examine la solicitud de imagen y las variables para comprobar que el “método de reserva” (la tercera parte del código "dividido" del ejemplo anterior) no está creando la solicitud de imagen en lugar del archivo [!DNL .JS]. Esto se puede determinar porque el método de "reserva" crea una solicitud de imagen con información mínima.
