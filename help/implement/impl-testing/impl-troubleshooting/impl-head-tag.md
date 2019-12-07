---
description: El código de Analytics crea un objeto de imagen, una imagen no visible que no se muestra en la página.
keywords: Analytics Implementation
title: Incluir código de Analytics en la etiqueta Head
topic: Developer and implementation
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Incluir código de Analytics en la etiqueta Head

El código de Analytics crea un objeto de imagen, una imagen no visible que no se muestra en la página.

>[!NOTE]
>
>Esta sección se aplica solo a la implementación de s_code.js heredada. [AppMeasurement para JavaScript 1.0](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) permite implementar la biblioteca y el código de página en la etiqueta `<head>`.

Anteriormente, un procedimiento de implementación habitual era colocar el código JavaScript de Analytics entre las etiquetas <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> y </head> . Al colocar el código entre estas etiquetas, se impedía que la imagen de 1 x 1 píxeles devuelta por la solicitud que enviaba los datos a los servidores de Adobe afectara al diseño de la página de ninguna manera. Cuando el código se coloca en el encabezado del documento, aparece antes en el código. Esto permite que se ejecute antes, lo que optimiza el recuento de las vistas de página para cargas de página parciales.

Algunos elementos del código requieren que el objeto body esté presente. Como los exploradores web ejecutan el código en el orden con el que lo reciben, si el código JavaScript de Analytics está en el encabezado del documento, se ejecuta antes de que exista el objeto body. Como resultado, la implementación no recopila datos de [!UICONTROL ClickMap] y el seguimiento automático de descargas de archivos o vínculos de [!UICONTROL salida] no está disponible. Tampoco recibirá datos sobre el tipo de conexión ni sobre la página de inicio del visitante. Colocar el código en el encabezado del documento funciona, pero el resultado es una versión muy limitada de Analytics y los usuarios podrían preguntarse por qué determinados informes y herramientas, como [!UICONTROL ClickMap], no están registrando datos.

El código de Analytics se puede colocar en cualquier lugar dentro de las etiquetas BODY (<BODY></BODY>) de una página HTML bien creada. Adobe recomienda colocar el código en un archivo de inclusión global, en la parte superior de la página (dentro de la etiqueta HTML body). El código se puede colocar en cualquier lugar de la página, con las siguientes excepciones:

* Si se coloca dentro de una tabla, publique el código únicamente dentro de las etiquetas <td></td> . Por ejemplo, no coloque el código entre dos etiquetas <tr> de <td> apertura.
* El código que configura las variables debe situarse después de la referencia al archivo s_code.js.
* Asegúrese de que las [!UICONTROL ID del grupo deinformes] de la variable *`s_account`* en el archivo s_code.js estén configuradas correctamente. Por lo general, la configuración de esta variable es correcta cuando se descarga código del Administrador de códigos para un grupo de informes determinado, o cuando la proporciona un consultor técnico de Adobe.

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

