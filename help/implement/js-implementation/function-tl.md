---
description: El seguimiento de las descargas de archivos y los vínculos de salida se puede realizar automáticamente en función de los parámetros configurados en el archivo de AppMeasurement para JavaScript.
keywords: Implementación de análisis
seo-description: El seguimiento de las descargas de archivos y los vínculos de salida se puede realizar automáticamente en función de los parámetros configurados en el archivo de AppMeasurement para JavaScript.
seo-title: Función s.tl() - Seguimiento de vínculos
solution: Analytics
subtopic: Seguimiento de vínculos
title: Función s.tl() - Seguimiento de vínculos
topic: Desarrollador e implementación
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 1ed1c6cd3fd6d29fa156cd4b2c4bdfe9120b3c61

---


# Función s.tl() - Seguimiento de vínculos

Si su organización prefiere tener más control sobre los vínculos que rastrear y su comportamiento, se recomienda el seguimiento manual de vínculos. Utilice la función s.tl() para enviar manualmente solicitudes de imagen de seguimiento de vínculos con el contenido exacto deseado. Si el seguimiento de vínculos básico es todo lo que se necesita, consulte `s.trackDownloadLinks` y `s.trackExitLinks` en [Variables](c-variables/configuration-variables.md)de configuración. Los vínculos personalizados no se pueden rastrear automáticamente.

> [!NOTE] El código de seguimiento de vínculos suele ser muy específico para el sitio y para las necesidades de informes. Adobe recomienda una experiencia de implementación previa o un consultor de implementación para comprender cómo utilizar esta función según sus necesidades comerciales.

## Sintaxis y ejemplos

Sintaxis básica:

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

Ejemplos básicos:

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true (requerido)

El primer argumento determina si el explorador espera hasta 500 ms antes de salir de la página. Si una solicitud de imagen se envía antes de 500 ms, la página se desplaza inmediatamente al vínculo donde se hizo clic.

* `this`:: Espere hasta 500 ms para que AppMeasurement tenga tiempo de enviar una solicitud de imagen. Valor predeterminado.
* `true`:: No espere. Si el vínculo sale de la página, es posible que no se envíe una solicitud de imagen.

La demora solo es necesaria cuando un vínculo abandona la página.

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (requerido)

El segundo argumento tiene tres valores válidos según el tipo de vínculo que desee capturar. Determina qué dimensión de Adobe Analytics llena la solicitud de imagen.

* `d`: Descargas de archivos
* `e`: Vínculos de salida
* `o`:: Vínculos personalizados

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName (requerido)

Este argumento puede ser cualquier valor personalizado de hasta 100 bytes. Determina el valor de dimensión en los informes.

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides (opcional)

Permite cambiar los valores de las variables para una sola llamada. Si utiliza el argumento doneAction y no tiene sobrescrituras de variables, utilice `null`.

### doneAction (opcional)

Especifica una acción de navegación que se ejecutará después de que se complete la llamada de seguimiento de vínculos. Requiere el uso de `s.useForcedLinkTracking` y `s.forcedLinkTrackingTimeout`. The doneAction variable can be the string `navigate`, which causes the method to set `document.location` to the href attribute of `linkObject`. La variable doneAction también puede ser una función que permita una mayor personalización.

Si se proporciona un valor para doneAction en un evento `onClick``false` con delimitador, debe devolver después de la llamada a `s.tl` para evitar la navegación predeterminada del explorador.
To mirror the default behavior and follow the URL specified by the href attribute, provide a string of `navigate` as the doneAction. De forma opcional, puede proporcionar su propia función para que se ocupe del evento de navegación pasando esta función como doneAction.

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## Uso de funciones de JavaScript con seguimiento de vínculos

Puede consolidar el código de seguimiento de vínculos en una función JavaScript independiente definida en la página o en un archivo JavaScript vinculado. Las llamadas se pueden realizar en la función onClick de cada vínculo.

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## Evitar recuentos de vínculos duplicados {#section_9C3F73DE758F4727943439DED110543C}

Es posible que los vínculos se cuenten dos veces en situaciones en las que el seguimiento automático de descargas de archivos o vínculos de salida captura normalmente el vínculo. For example, if you are tracking PDF downloads automatically, an `s.tl` call results in a duplicate download count:

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

Para asegurarse de que el vínculo no se cuenta por duplicado, use la siguiente función JavaScript modificada:

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
