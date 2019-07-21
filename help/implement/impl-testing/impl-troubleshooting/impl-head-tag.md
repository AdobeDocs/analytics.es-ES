---
description: El código de Analytics crea un objeto de imagen, una imagen no visible que no se muestra en la página.
keywords: Implementación de Analytics
seo-description: El código de Analytics crea un objeto de imagen, una imagen no visible que no se muestra en la página.
seo-title: Colocar código de Analytics en la etiqueta head
solution: Analytics
title: Colocar código de Analytics en la etiqueta head
topic: Desarrollador e implementación
uuid: e 8 f 91 d 3 c-cb 72-454 d -9 bd 4-ff 54 d 83 d 981 f
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Colocar código de Analytics en la etiqueta head

El código de Analytics crea un objeto de imagen, una imagen no visible que no se muestra en la página.

>[!NOTE]
>
>Esta sección solo se aplica a la implementación s_ code. js heredada. [Appmeasurement para JavaScript 1.0](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) permite implementar la biblioteca y el código de página en `<head>` la etiqueta.

Anteriormente, una práctica de implementación común era colocar el código JavaScript de Analytics entre la variable <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> y </head> etiquetas. Al colocar el código entre estas etiquetas, se impedía que la imagen de 1 x 1 píxeles devuelta por la solicitud que enviaba los datos a los servidores de Adobe afectara al diseño de la página de ninguna manera. Cuando el código se coloca en el encabezado del documento, aparece antes en el código. Esto permite que se ejecute antes, lo que optimiza el recuento de las vistas de página para cargas de página parciales.

Algunos elementos del código requieren que el objeto body esté presente. Como los exploradores web ejecutan el código en el orden con el que lo reciben, si el código JavaScript de Analytics está en el encabezado del documento, se ejecuta antes de que exista el objeto body. Como resultado, la implementación no recopila datos de [!UICONTROL ClickMap] y el seguimiento automático de descargas de archivos o vínculos de [!UICONTROL salida] no está disponible. Tampoco recibirá datos sobre el tipo de conexión ni sobre la página de inicio del visitante. Colocar el código en el encabezado del documento funciona, pero el resultado es una versión muy limitada de Analytics y los usuarios podrían preguntarse por qué determinados informes y herramientas, como [!UICONTROL ClickMap], no están registrando datos.

El código de Analytics se puede colocar en cualquier lugar dentro de las etiquetas BODY (<BODY></BODY>) de una página HTML bien formada. Adobe recomienda colocar el código en un archivo de inclusión global, en la parte superior de la página (dentro de la etiqueta HTML body). El código se puede colocar en cualquier lugar de la página, con las siguientes excepciones:

* Si se coloca dentro de una tabla, publique el código solamente dentro de la <td></td> etiquetas. Por ejemplo, no coloque el código entre una apertura <tr> etiqueta y apertura <td> etiqueta.
* El código que configura las variables debe situarse después de la referencia al archivo s_code.js.
* Make certain that the [!UICONTROL report suite ID]s in the *`s_account`* variable in the s_code.js file are set correctly. Por lo general, la configuración de esta variable es correcta cuando se descarga código del Administrador de códigos para un grupo de informes determinado, o cuando la proporciona un consultor técnico de Adobe.

Si desea integrar Analytics con Target, el archivo de inclusión JavaScript debe colocarse en la parte inferior de la página. El siguiente ejemplo muestra la ubicación correcta del código de Analytics:

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3. 
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 
```

