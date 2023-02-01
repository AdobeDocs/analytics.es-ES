---
title: Implementar Adobe Analytics con la extensión de Analytics
description: Obtenga información sobre cómo implementar Adobe Analytics mediante etiquetas y la extensión de Analytics
feature: Launch Implementation
source-git-commit: aef1d613437688b7eed704b227c41e4fbe4677dd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 58%

---

# Implementar Adobe Analytics con la extensión de Analytics

Durante toda la vida útil de Adobe Analytics, Adobe ha ofrecido varios métodos diferentes para implementar código en su sitio para la recopilación de datos. El método recomendado actual de Adobe es mediante etiquetas en Adobe Experience Platform.

Las etiquetas en Adobe Experience Platform son una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.

Todos los clientes con un contrato activo de Adobe Experience Cloud pueden utilizar etiquetas. Si no está seguro de tener acceso, póngase en contacto con uno de los administradores del sistema de Experience Cloud de su organización.

Una visión general de alto nivel de las tareas de implementación:



![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td> 1</td>
<td>Asegúrese de que <b>definición de un grupo de informes</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Creación de una capa de datos</b>para administrar el seguimiento de los datos del sitio web.</td>
<td>
<a href="../prepare/data-layer.md">Creación de una capa de datos</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Crear una propiedad de etiqueta</b>. Las propiedades son contenedores generales que se utilizan para hacer referencia a los datos de administración de etiquetas.</td>
<td><a ref="../launch/create-analytics-property.md">Creación de una propiedad de etiquetas de Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Instalación de la extensión de Analytics</b> en la propiedad tag . Configure la extensión de Analytics para enviar datos a Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en">Información general sobre la extensión Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Implementar en un entorno de desarrollo</b>. Tenga un entorno en el que pueda iterar en el desarrollo de etiquetas.</td>
<td><a href="./deploy-dev.md">Integrar una implementación de Analytics en un entorno de desarrollo</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validación y publicación para producción</b>. Agregue la propiedad tag al sitio web. A continuación, utilice elementos de datos, reglas, etc. para personalizar la implementación.</td>
<td><a href="./validate-publish-prod.md">Validación de una implementación de desarrollo y publicación en producción</a></td>
</tr>

</table>

## Recursos adicionales

Las etiquetas se pueden personalizar en gran medida. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#): Descubra cómo funciona la interfaz y qué extensiones están disponibles.

- [Variables de implementación](../vars/overview.md): Determine qué variables desea enviar a los servidores de recopilación de datos.
