---
title: Implementar Adobe Analytics usando la extensión de Analytics
description: Obtenga información sobre cómo implementar Adobe Analytics usando etiquetas y la extensión de Analytics
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 83%

---

# Implementar Adobe Analytics usando la extensión de Analytics

Durante toda la vida útil de Adobe Analytics, Adobe ha ofrecido varios métodos diferentes para implementar código en su sitio para la recopilación de datos. El método que recomienda actualmente Adobe es a través de [Etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es) en Adobe Experience Platform.

Las etiquetas en Adobe Experience Platform son una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.

Todos los clientes con un contrato activo de Adobe Experience Cloud pueden utilizar etiquetas. Si no está seguro de tener acceso, póngase en contacto con uno de los administradores del sistema de Experience Cloud de su organización.

Una información general de alto nivel de las tareas de implementación:



![Cómo implementar Adobe Analytics mediante el flujo de trabajo de la extensión de Analytics, tal como se describe en esta sección.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td> 1</td>
<td>Asegúrese de haber <b>definido un grupo de informes</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Creación de una capa de datos</b> para administrar el seguimiento de los datos del sitio web.</td>
<td>
<a href="../prepare/data-layer.md">Creación de una capa de datos</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Crear una propiedad de etiquetas</b>. Las propiedades son contenedores generales que se utilizan para hacer referencia a los datos de administración de etiquetas.</td>
<td><a href="../launch/create-analytics-property.md">Creación de una propiedad de etiquetas de Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Instalación de la extensión de Analytics</b> en la propiedad de la etiqueta. Configure la extensión de Analytics para enviar datos a Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=es">Información general sobre la extensión Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Implementar en un entorno de desarrollo</b>. Utilice un entorno en el que pueda iterar en el desarrollo de etiquetas.</td>
<td><a href="./deploy-dev.md">Integrar una implementación de Analytics en un entorno de desarrollo</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validación y publicación para producción</b>. Incruste el código para incluir la propiedad de etiquetas en las páginas del sitio web. A continuación, utilice elementos de datos, reglas, etc. para personalizar la implementación.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=es#embed-code">Código incrustado</a><br/><a href="./validate-publish-prod.md">Validar una implementación de desarrollo y publicar en producción</a></td>
</tr>

</table>

## Recursos adicionales

Las etiquetas se pueden personalizar en gran medida. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#): descubra cómo funciona la interfaz y qué extensiones están disponibles.

- [Variables de implementación](../vars/overview.md): determine qué variables desea enviar a los servidores de recopilación de datos.
