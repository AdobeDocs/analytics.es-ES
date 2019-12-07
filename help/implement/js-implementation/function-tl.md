---
description: El seguimiento de las descargas de archivos y los vínculos de salida se puede realizar automáticamente en función de los parámetros configurados en el archivo de AppMeasurement para JavaScript.
keywords: Analytics Implementation
subtopic: Link tracking
title: Función s.tl() - Seguimiento de vínculos
topic: Developer and implementation
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Función s.tl() - Seguimiento de vínculos

Si su organización prefiere tener más control sobre los vínculos quiere rastrear y su comportamiento, se recomienda utilizar un seguimiento manual de vínculos. Utilice la función s.tl() para enviar manualmente solicitudes de imagen de seguimiento de vínculos con el contenido exacto deseado. Si el seguimiento de vínculos básico es todo lo que se necesita, consulte `s.trackDownloadLinks` y `s.trackExternalLinks` en [Variables de configuración](c-variables/configuration-variables.md). Los vínculos personalizados no se pueden rastrear automáticamente.

> [!NOTE] El código de seguimiento de vínculos suele ser muy específico para el sitio y para las necesidades derivadas de los informes. Se recomienda contar con experiencia de implementación previa o con un consultor de implementación para comprender cómo utilizar esta función de acuerdo con sus necesidades comerciales.

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

* `this`: Esperar hasta 500 ms para que AppMeasurement tenga tiempo de enviar una solicitud de imagen. Valor predeterminado.
* `true`: No esperar. Si el vínculo sale de la página, es posible que no se envíe una solicitud de imagen.

La demora solo es necesaria cuando un vínculo abandona la página.

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (requerido)

El segundo argumento tiene tres posibles valores, en función del tipo de vínculo que se desea capturar. Determina qué dimensión de Adobe Analytics se utiliza en la solicitud de imagen.

* `d`: Descargas de archivos
* `e`: Vínculos de salida
* `o`: Vínculos personalizados

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

Especifica una acción de navegación que se ejecutará después de que se complete la llamada de seguimiento de vínculos. Requiere el uso de `s.useForcedLinkTracking` y `s.forcedLinkTrackingTimeout`. La variable doneAction puede ser la cadena `navigate`, lo que hace que el método configure `document.location` como el atributo href de `linkObject`. La variable doneAction también puede ser una función que permita una mayor personalización.

Si se proporciona un valor para doneAction en un evento `onClick``false` con delimitador, debe devolver después de la llamada a `s.tl` para evitar la navegación predeterminada del explorador.
Para imitar el comportamiento predeterminado y seguir la dirección URL especificada por el atributo href, proporcione una cadena `navigate` como doneAction. De forma opcional, puede proporcionar su propia función para que se ocupe del evento de navegación pasando esta función como doneAction.

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

Puede ocurrir que un vínculo se cuente dos veces si suele capturarse mediante la descarga automática de archivos o en el seguimiento de vínculos de salida. Por ejemplo, si rastrea descargas de PDF de forma automática, una llamada a `s.tl` generará un recuento de descargas duplicado:

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
