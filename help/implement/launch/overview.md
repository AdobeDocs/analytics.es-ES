---
title: Implementación con etiquetas en Adobe Experience Platform
description: Obtenga información sobre cómo implementar Adobe Analytics mediante etiquetas
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 47%

---

# Implementación con etiquetas en Adobe Experience Platform

>[!NOTE]
>Adobe Experience Platform Launch se ha convertido en un conjunto de tecnologías de recopilación de datos en Experience Platform. Como resultado, se han implementado varios cambios terminológicos en la documentación del producto. Consulte el siguiente [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obtener una referencia consolidada de los cambios terminológicos.

Durante toda la vida útil de Adobe Analytics, Adobe ha ofrecido varios métodos diferentes para implementar código en su sitio para la recopilación de datos. El método de recomendación actual de Adobe es mediante etiquetas en Adobe Experience Platform.

Etiquetas en Adobe Experience Platform es una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Adobe ofrece integraciones con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio.

Todos los clientes con un contrato activo de Adobe Experience Cloud pueden utilizar etiquetas. Si no está seguro de tener acceso, póngase en contacto con uno de los administradores del sistema de Experience Cloud de su organización.

## Flujo de trabajo general

Para que una implementación se ejecute mediante etiquetas, siga estos pasos:

1. **Obtener acceso a las etiquetas**: Puede obtener acceso a las etiquetas de Platform a través de un administrador del sistema de su organización.
2. **Crear una propiedad** de etiqueta: Las propiedades son contenedores generales que se utilizan para hacer referencia a los datos de administración de etiquetas.
3. **Implementar en un entorno de desarrollo**: Utilice un entorno en el que pueda iterar en el desarrollo de etiquetas.
4. **Validar y publicar para producción**: Asegúrese de que todo funcione y, a continuación, publíquelo para su producción.

Consulte [Crear una propiedad de etiqueta de Analytics](create-analytics-property.md) para empezar.

## Recursos adicionales

Las etiquetas pueden personalizarse en gran medida. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

* [Documentación](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#) de etiquetas: Descubra cómo funciona la interfaz y qué extensiones están disponibles.
* [Extensión de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en): Utilice la extensión de Analytics para enviar datos a Adobe Analytics.
* [Variables de implementación](../vars/overview.md): Determine qué variables desea enviar a los servidores de recopilación de datos.
