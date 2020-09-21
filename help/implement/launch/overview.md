---
title: Introducción a la implementación con Launch
description: Obtenga información sobre cómo implementar Adobe Analytics mediante Adobe Experience Platform Launch
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35
workflow-type: ht
source-wordcount: '302'
ht-degree: 100%

---


# Introducción a la implementación con Launch

Durante toda la vida útil de Adobe Analytics, Adobe ha ofrecido varios métodos diferentes para implementar código en su sitio para la recopilación de datos. El método de recomendación actual de Adobe es a través de Adobe Experience Platform Launch.

Launch es una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.

Todos los clientes con un contrato activo de Adobe Experience Cloud pueden utilizar Launch. Si no está seguro de tener acceso, póngase en contacto con uno de los administradores del sistema de Experience Cloud de su organización.

## Flujo de trabajo general

Para ejecutar una implementación con Launch, siga estos pasos:

1. **Obtener acceso a Launch**: Puede obtener acceso a Launch a través de un administrador del sistema de su organización.
2. **Crear una propiedad**: Las propiedades son contenedores generales que se utilizan para hacer referencia a los datos de administración de etiquetas.
3. **Implementar en un entorno de desarrollo**: Utilice un entorno en el que pueda iterar en el desarrollo de etiquetas.
4. **Validar y publicar para producción**: Asegúrese de que todo funcione y, a continuación, publíquelo para su producción.

Consulte [Creación de una propiedad de Analytics en Adobe Experience Platform Launch](create-analytics-property.md) para empezar.

## Recursos adicionales

Launch se puede personalizar. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

* [Documentación de Launch](https://docs.adobe.com/content/help/es-ES/launch/using/overview.html): Descubra cómo funciona la interfaz y qué extensiones están disponibles.
* [Extensión de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html): Utilice la extensión de Analytics para enviar datos a Adobe Analytics.
* [Variables de implementación](../vars/overview.md): Determine qué variables desea enviar a los servidores de recopilación de datos.
