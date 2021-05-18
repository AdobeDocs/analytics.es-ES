---
title: Integrar módulo
description: El módulo Integrate permite a los socios de Adobe integrar sus esfuerzos de recopilación de datos con su organización.
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 98%

---

# Integrar módulo

El módulo Integrate permite a los socios de Adobe integrar sus esfuerzos de recopilación de datos con su organización. Esta integración ofrece la oportunidad de establecer una conexión de datos bidireccional. Generalmente, el uso del módulo Integrate lo gestiona un socio de Adobe.

>[!NOTE]
>
>La solicitud de datos de socios en la implementación puede aumentar los retrasos entre la carga de página y los datos enviados a los servidores de recopilación de datos de Adobe. Si un visitante carga una página nueva antes de que se envíen los datos, esa página no se registra.

## Flujo de trabajo del módulo Integrate

1. Un visitante del sitio carga una página que inicia una solicitud `get` de datos de socio.
2. El socio de Adobe recibe la solicitud `get` y empaqueta las variables adecuadas en un objeto JSON. Se devuelve el objeto JSON.
3. El sitio recibe el objeto JSON y realiza llamadas a `setVars` para asignar la información contenida en el objeto JSON a variables de Adobe Analytics.
4. Se envía una solicitud de imagen a los servidores de recopilación de datos de Adobe.

## Implementación del módulo Integrate

Una organización que trabaje con un socio de Adobe puede utilizar estos pasos para empezar a utilizar correctamente el módulo Integrate.

### Obtención del código del módulo Integrate

Para obtener el código del módulo, es necesario que un usuario tenga acceso al Administrador de productos o pertenezca a un perfil de producto con acceso al Administrador de códigos. El método para obtener el código del módulo es el mismo para todos los métodos de implementación, incluido Adobe Experience Platform Launch.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
1. En la barra de navegación superior, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Administrador de códigos]**.
1. Descargue la biblioteca de AppMeasurement de JavaScript más reciente.
1. Una vez descargado, descomprima el archivo y busque `AppMeasurement_Module_Integrate.js`.

### Coloque el módulo Integrate en la implementación

La implementación del módulo Integrate en su sitio requiere acceso a Adobe Experience Platform Launch. Si utiliza una implementación de JavaScript heredada, se requiere acceso al código fuente del sitio web de la organización.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad Launch que desee editar.
3. Haga clic en la pestaña Extensiones y, a continuación, haga clic en Configurar en Adobe Analytics.
4. Abra “Configurar rastreador con código personalizado” y haga clic en “Abrir editor”.
5. Pegue el código del módulo Integrate en la ventana modal de código. Haga clic en Guardar una vez completada.

## Métodos del módulo Integrate

Una vez implementado el módulo Integrate, utilice estos métodos para configurarlo y enviar y recibir datos del socio de Adobe deseado.

### Agregue

El método `add` crea una instancia de un objeto de socio, que sirve como almacén intermedio de datos variables al compartir datos entre sistemas de socios y la implementación. Este método es necesario para todas las integraciones. Si se utilizan varios socios en una sola implementación, se debe utilizar un objeto de socio independiente para cada socio único.

```JavaScript
s.Integrate.add("<partner_name>");
```

Su organización suele trabajar con un socio de Adobe para determinar el valor del nombre del socio.

### beacon

El método `beacon` crea una solicitud de imagen y marca la dirección URL especificada. Estas solicitudes de imagen son diferentes a las solicitudes de imagen estándar. El método de señalización suele enviar datos al socio de Adobe en lugar de a los servidores de recopilación de datos de Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

Su organización suele trabajar con el socio de Adobe para determinar el valor del nombre del socio. Las cadenas de consulta incluidas en la dirección URL son opcionales y dependen del socio. El módulo Integrate incluye automáticamente una cadena de consulta que contiene un número aleatorio para evitar el almacenamiento en caché del explorador.

### delay

Adobe está trabajando con sus equipos internos para documentar este método.

### get

El método `get` permite a un cliente importar variables de socio y almacenarlas en el objeto de socio. Una vez que los datos están en el objeto de socio, se pueden asignar a variables de Analytics y enviar en una solicitud de imagen. Este método llama a una dirección URL, que apunta a un objeto JSON que contiene los datos deseados.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nombre del socio**: Su organización suele trabajar con el socio de Adobe para determinar el valor del nombre del socio.
* **Dirección URL del objeto JSON**: Dirección URL de un objeto JSON que contiene las variables de socio que se van a incorporar en una solicitud de imagen.
* **Parámetros de cadena de consulta**: Información de cuenta de socio que identifica a su organización en el sistema del socio. El socio de Adobe utiliza esta información para identificar el conjunto de datos.

El módulo Integrate agrega automáticamente más cadenas de consulta a la dirección URL. Una cadena de consulta var especifica el nombre del objeto JSON que el módulo espera del socio. También se agrega un número aleatorio para evitar el almacenamiento en caché del explorador.

### ready

Adobe está trabajando con sus equipos internos para documentar este método.

### useVars

El método `useVars` permite al cliente compartir valores de variables con un socio de Adobe.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

Su organización suele trabajar con un socio de Adobe para determinar los valores del nombre del socio y las variables que utiliza el socio.

### setVars

El método `setVars` permite al cliente rellenar variables de Analytics mediante los datos del socio recuperados. Los datos del socio pueden ser el resultado de un método `get`, una asignación estática o cualquier otro mecanismo que rellene el objeto del socio con datos.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

Su organización suele trabajar con un socio de Adobe para determinar los valores del nombre del socio y las variables que utiliza el socio.

### script

El método `script` permite que un socio de Adobe llame a JavaScript adicional desde el sitio del socio si se cumplen determinadas condiciones (por ejemplo, si se establece la variable de campaña).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

Su organización suele trabajar con el socio de Adobe para determinar el valor del nombre del socio. Las cadenas de consulta incluidas en la dirección URL son opcionales y dependen del socio. El módulo Integrate incluye automáticamente una cadena de consulta que contiene un número aleatorio para evitar el almacenamiento en caché del explorador.
