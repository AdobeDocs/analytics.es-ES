---
title: Modo de implementación
description: Obtenga información sobre la experiencia de los usuarios que compran sus productos por primera vez a la hora de poner en marcha la implementación de Adobe Analytics.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Modo de implementación

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

La ventana modal “Bienvenido a Adobe Analytics” proporciona un flujo de trabajo simplificado para crear un grupo de informes. Adobe recomienda utilizar este flujo de trabajo siempre que se necesiten más grupos de informes en su organización.

![Captura de pantalla de Modal](assets/implementation-modal.png)

## Requisitos previos

Su Adobe ID debe tener acceso a Adobe Analytics y a Adobe Experience Platform Launch. Si no tiene acceso a Launch, puede acabar en un bucle de autenticación en el que se le pedirá que compruebe sus credenciales indefinidamente. Póngase en contacto con un administrador del sistema de su organización para obtener acceso a Launch.

## Acceda al modal

Acceda al modal para crear un grupo de informes siguiendo los pasos siguientes.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrículas en la parte superior y, a continuación, haga clic en [!UICONTROL Adobe Analytics].
3. Si aún no ha creado un grupo de informes, el modal se muestra automáticamente. Si existe un grupo de informes para este proveedor de inicio de sesión, haga clic en el icono Ayuda en la parte superior derecha y, a continuación, haga clic en [!UICONTROL Bienvenido a Adobe Analytics].

> [!NOTE] La opción [!UICONTROL Bienvenido a Adobe Analytics] solo aparece si inicia sesión a través de Adobe Experience Cloud. Si inicia sesión a través de dominios heredados, el modal no está disponible.

## Crear un grupo de informes

Haga clic en el botón [!UICONTROL Iniciar configuración] para iniciar el flujo de trabajo de creación de grupos de informes.

![Asistente de RS](assets/analytics-implementation-rs-wizard.png)

### Tipo de propiedad

El tipo de propiedad ayuda a Adobe a determinar algunos ajustes del servidor en función de dónde se va a implementar Analytics.

* **Sitio web**: Si quiere implementar Adobe Analytics solo para un sitio web.
* **Aplicación móvil nativa**: Si quiere implementar Adobe Analytics solo para una aplicación móvil.
* **Ambos**: Si este grupo de informes contiene datos para un sitio web y una aplicación móvil.

### Sectores

Especifique el modelo empresarial principal. Esta configuración ayuda a Adobe a preconfigurar algunos nombres y configuraciones de variables en función de su modelo empresarial principal.

### Capa de datos

Una [capa de datos](data-layer.md) es un objeto JavaScript que organiza todas las variables utilizadas en la implementación en una sola ubicación útil. Consulte [Capas de datos](data-layer.md) para obtener más información

### Repositorio de datos

Asigne un nombre reconocible al grupo de informes. El ID del grupo de informes (RSID) se genera automáticamente según el nombre reconocible y el proveedor de inicio de sesión.

### Zona horaria

Compruebe que Adobe ha detectado la zona horaria correcta para el grupo de informes.

### Vistas de la página estimadas por día

Calcule el tráfico que recibe su sitio web o aplicación por día. Esta información permite a Adobe asignar la cantidad correcta de recursos de procesamiento a su grupo de informes.

### Moneda base

Determine en qué moneda almacena los valores monetarios el grupo de informes.

> [!IMPORTANT] Asegúrese de indicar la moneda correcta, especialmente si tiene requisitos de informes en relación con los ingresos. Es difícil cambiar la moneda base después de que comience la recopilación de datos.

## Recursos de implementación

Una vez creado el grupo de informes, debe elegir una de las dos opciones para continuar con la implementación:

* **Vaya a Adobe Experience Platform Launch**: Le redirige a [launch.adobe.com](https://launch.adobe.com) para configurar la implementación y descargar el código de implementación. Consulte [Implementación con Launch](../launch/overview.md) Adobe recomienda usar Launch en la mayoría de los casos.
* **Descargar código de implementación**: Proporciona un vínculo directo para descargar archivos JavaScript para una implementación manual de JavaScript. Consulte [AppMeasurement para JavaScript](../js/overview.md).
