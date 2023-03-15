---
title: Implementar Adobe Analytics con AppMeasurement para JavaScript
description: Obtenga información sobre cómo implementar Adobe Analytics mediante JavaScript sin un sistema de administración de etiquetas.
feature: Implementation Basics
source-git-commit: aef1d613437688b7eed704b227c41e4fbe4677dd
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 58%

---

# Implementar Adobe Analytics con AppMeasurement para JavaScript

Históricamente, AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics. Sin embargo, con la creciente popularidad de los sistemas de Tag Management, se recomienda utilizar [etiquetas en Adobe Experience Platform](../launch/overview.md).

Una información general de alto nivel de las tareas de implementación:

![Información general sobre la implementación de Adobe Analytics con AppMeasurement](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Tarea</b></th><th style="width:20%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td><td>Asegúrese de haber <b>definido un grupo de informes</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td><td><b>Descargue el código JavaScript necesario para AppMeasurement</b> de Administrador de códigos. Descomprima el archivo.</td><td><a href="../../admin/admin/code-manager-admin.md">Administrador de códigos</a></td>
</tr>

<tr>
<td>3</td><td><b>Añadir <code>AppMeasurement.js</code> al archivo de plantilla del sitio web</b>. El código contiene las bibliotecas necesarias para enviar datos al Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Defina las variables de configuración de <code>AppMeasurement.js</code></b>. Cuando se crea una instancia del objeto de Analytics, estas variables garantizan que la configuración de recopilación de datos sea correcta.

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">Variables de configuración</a></td>
</tr>

<tr>
<td>5</td><td><b>Defina las variables de nivel de página dentro del código de página del sitio</b>. Estas variables determinan la dimensión y las métricas específicas que se envían a Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Variables de página</a></td>
</tr>

<tr>
<td>6</td><td><b>Envíe los datos al Adobe mediante la variable <code>t()</code> método</b>, cuando se definan todas las variables de página.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">método t()</a></td>
</tr>

<tr>
<td>7</td><td><b>Ampliación y validación de la implementación</b> antes de llevarlo a producción.</b></td><td></td>
</tr>

</table>

## Recursos adicionales

- [Información general sobre variables, funciones, métodos y complementos](../vars/overview.md)
