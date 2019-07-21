---
title: Integrar módulo
seo-title: Módulo Integrate para Adobe Analytics
description: El módulo Integrate permite a los socios de Adobe integrar sus esfuerzos de recopilación de datos con su organización.
seo-description: El módulo Integrate permite a los socios de Adobe integrar sus esfuerzos de recopilación de datos con su organización.
translation-type: tm+mt
source-git-commit: dae73042ace20eded9d0caf690a14203827f903a

---


# Integrar módulo

El módulo Integrate permite a los socios de Adobe integrar sus esfuerzos de recopilación de datos con su organización. Esta integración proporciona la oportunidad de una conexión de datos bidireccional. Normalmente, el uso del módulo Integrate es administrado por un socio de Adobe.

> [!NOTE] La solicitud de datos de socio en la implementación puede aumentar los retrasos entre la carga de página y los datos enviados a los servidores de recopilación de datos de Adobe. Si un visitante carga una página nueva antes de que se envíen los datos, esa página no se registra.

## Flujo de trabajo de módulo integrado

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. Se devuelve el objeto JSON.
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. Se envía una solicitud de imagen a los servidores de recopilación de datos de Adobe.

## Implementación del módulo Integrate

Una organización que trabaja con un socio de Adobe puede utilizar estos pasos para empezar a utilizar el módulo Integrate con éxito.

### Obtener el código de Integrate Module

La obtención del código de módulo requiere un usuario con acceso de administrador de productos o que pertenezca a un perfil de producto con acceso al Administrador de códigos. El método para obtener el código del módulo es el mismo para todos los métodos de implementación, incluido el lanzamiento de la Plataforma de Adobe Experience.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Haga clic en el icono 9 cuadrado en la esquina superior derecha y, a continuación, haga clic en el logotipo de color de color.
1. In the top navigation, click [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. Descargue la última biblioteca de appmeasurement de JavaScript.
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### Coloque el módulo Integrate en su implementación

La implementación del módulo Integrate en su sitio requiere acceso a Adobe Experience Platform Launch. Si utiliza una implementación javascript heredada, es necesario acceder al código fuente del sitio Web de su organización.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Haga clic en la propiedad Launch que desee editar.
3. Haga clic en la ficha Extensiones y, a continuación, haga clic en Configurar en Adobe Analytics.
4. Abra el acordeón'Configurar rastreador utilizando el código personalizado'y haga clic en ' &lt;/&gt; Abrir editor '.
5. Pegue el código del módulo Integrate en la ventana modal del código. Haga clic en Guardar una vez completada.

## Métodos del módulo Integrate

Una vez implementado el módulo Integrate, utilice estos métodos para configurarlo para enviar y recibir datos del socio de Adobe que desee.

### agregar

The `add` method instantiates a partner object, which serves as an intermediate store of variable data when sharing data between partner systems and your implementation. Este método es necesario para todas las integraciones. Se debe utilizar un objeto de socio independiente para cada socio único si se utilizan varios socios en una sola implementación.

```JavaScript
s.Integrate.add("<partner_name>");
```

Su organización generalmente trabaja con un socio de Adobe para determinar el valor del nombre del socio.

### señalización

The `beacon` method creates an image request and points it to the specified URL. Estas solicitudes de imagen son diferentes a las solicitudes de imagen estándar. El método de señalización suele enviar datos al socio de Adobe en lugar de a los servidores de recopilación de datos de Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

Su organización generalmente trabaja con el socio de Adobe para determinar el valor del nombre del socio. Las cadenas de consulta incluidas en la dirección URL son opcionales y dependen del socio. El módulo Integrate incluye automáticamente una cadena de consulta que contiene un número aleatorio para evitar el almacenamiento en caché del navegador.

### delay

Adobe está trabajando con equipos internamente para documentar este método.

### get

The `get` method lets a client import partner variables and store them in the partner object. Una vez que los datos se encuentran en el objeto asociado, se pueden asignar a variables de Analytics y enviarlos en una solicitud de imagen. Este método llama a una dirección URL que apunta a un objeto JSON que contiene los datos deseados.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nombre del socio:** Su organización generalmente trabaja con el socio de Adobe para determinar el valor del nombre del socio.
* **URL al objeto JSON:** La URL de un objeto JSON que contiene las variables de socio que se van a incorporar a una solicitud de imagen.
* **Parámetros de cadena de consulta:** Información de la cuenta de socio que identifica a su organización en el sistema del socio. El socio de Adobe utiliza esta información para identificar el conjunto de datos.

El módulo Integrate agrega automáticamente más cadenas de consulta a la URL. Una cadena de consulta var especifica el nombre del objeto JSON que espera el módulo del socio. También se agrega un número aleatorio para evitar el almacenamiento en caché del navegador.

### ready

Adobe está trabajando con equipos internamente para documentar este método.

### Usevars

The `useVars` method lets the client share variable values with an Adobe partner.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

Su organización generalmente trabaja con un socio de Adobe para determinar los valores del nombre del socio y las variables que utiliza el socio.

### Setvars

The `setVars` method lets the client populate Analytics variables using partner data retrieved. Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

Su organización generalmente trabaja con un socio de Adobe para determinar los valores del nombre del socio y las variables que utiliza el socio.

### script

The `script` method lets an Adobe partner to call additional JavaScript from the partner site if certain conditions are met (for example, if the campaign variable is set).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

Su organización generalmente trabaja con el socio de Adobe para determinar el valor del nombre del socio. Las cadenas de consulta incluidas en la dirección URL son opcionales y dependen del socio. El módulo Integrate incluye automáticamente una cadena de consulta que contiene un número aleatorio para evitar el almacenamiento en caché del navegador.
