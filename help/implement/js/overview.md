---
title: Implemente Adobe Analytics con AppMeasurement para JavaScript
description: Obtenga información sobre cómo implementar Adobe Analytics mediante JavaScript sin un sistema de administración de etiquetas.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
TQID: https://experienceleague.adobe.com/QScNJBw6-Xn-gQCJBBxVT6melUpnyy6VIKrzvnDzJyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 100%

---

# Implemente Adobe Analytics con AppMeasurement para JavaScript

Históricamente, AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics. Sin embargo, con la creciente popularidad de los sistemas de Tag Management, se recomienda utilizar [etiquetas en Adobe Experience Platform](../launch/overview.md).

Una información general de alto nivel de las tareas de implementación:

![Cómo implementar Adobe Analytics con AppMeasurement para Javascript, tal como se describe en esta sección.](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Tarea</b></th><th style="width:20%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td><td>Asegúrese de haber <b>definido un grupo de informes</b></td><td><a href="../../admin/tools/manage-rs/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td><td><b>Descargue el código JavaScript necesario para AppMeasurement</b> desde el Administrador de códigos. Descomprima el archivo.</td><td><a href="../../admin/tools/code-manager-admin.md">Administrador de códigos</a></td>
</tr>

<tr>
<td>3</td><td><b>Añada <code>AppMeasurement.js</code> al archivo de plantilla del sitio web</b>. Este código contiene las bibliotecas necesarias para enviar datos a Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Defina las variables de configuración en <code>AppMeasurement.js</code></b>. Cuando se cita el objeto de Analytics, estas variables garantizan que la configuración de recopilación de datos sea correcta.

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
<td>5</td><td><b>Defina las variables a nivel de página dentro del código de página del sitio</b>. Estas variables determinan la dimensión y las métricas específicas que se envían a Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Variables de página</a></td>
</tr>

<tr>
<td>6</td><td><b>Envíe los datos a Adobe mediante el método <code>t()</code></b>, cuando se definan todas las variables de página.

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
