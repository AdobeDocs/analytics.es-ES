---
description: Variables para la administración de consentimiento en Privacidad de datos.
seo-description: Variables para la administración de consentimiento en Privacidad de datos.
seo-title: Variables de administración de consentimiento
solution: Analytics
title: Variables de administración de consentimiento
topic: Herramientas de administración
translation-type: tm+mt
source-git-commit: 492e9405c82183f6beb6588cd0dc039fe15350f7

---


# Variables de administración de consentimiento

Para proporcionar asistencia adicional en la administración de datos de privacidad, hay disponible un conjunto de variables reservadas que se pueden utilizar junto con variables de datos de contexto específicas.
Estas variables de administración de consentimiento proporcionan un marco fácil de usar para capturar el estado de consentimiento en cada visita de análisis.

## Variables

* Exclusión en la administración de consentimiento
   * Variable reservada: Prop de lista
   * Tipo: Cadena delimitada por comas
   * Contiene:
      * `contextData.['cm.ssf']=1` mostrado como SSF
      * `contextData.['opt.dmp']=N` mostrado como DMP
      * `contextData.['opt.sell']=N` mostrado como SELLO

* Inclusión en la administración de consentimiento
   * Variable reservada: Prop de lista
   * Tipo: Cadena delimitada por comas
   * Contiene:
      * `contextData.['opt.dmp']=Y` mostrado como DMP
      * `contextData.['opt.sell']=Y` mostrado como SELLO

## Creación de informes

Las variables de administración de consentimiento se pueden habilitar mediante una nueva configuración de privacidad disponible en la Consola de administración de Analytics.

Cada grupo de informes se puede configurar para:
1. En Informes y análisis, haga clic en Administración &gt; Grupos de informes.
1. Select the report suite(s) where you are collecting media data and click [!UICONTROL Edit Settings &gt; Privacy Management]

   ![](assets/rsm-privacy-select.png)

1. Haga clic en el botón [!UICONTROL Activar informes] de privacidad de datos.  Nota: Una vez estas variables estén activadas, no se pueden desactivar.

   ![](assets/rsm-privacy-enable.png)

1. Una vez activado, verá un mensaje de confirmación.

   ![](assets/rsm-privacy-config.png)

1. Las variables reservadas ahora están disponibles para los informes.  Consulte Opción de exclusión de administración de consentimiento y inclusión de administración de consentimiento.

   ![](assets/rsm-privacy-reports.png)

## Implementación

Se han predefinido tres variables de datos de contexto para que funcionen con las variables reservadas de gestión de consentimiento.  Depende de cada ingeniero de implementación determinar cómo administrar y mantener la configuración de estas variables.

Consulte Variables [de datos de](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) contexto para obtener instrucciones generales sobre cómo implementar variables de datos de contexto.

### SSF

* Datos de contexto: `contextData.['cm.ssf']`
* Valores aceptados:
   * `1` - Al enviar el valor `1`, esto indica que el reenvío de servidor está en estado de exclusión. El valor `1` asociado con esta variable bloqueará el uso compartido de esta visita con Adobe Audience Manager. Consulte Cumplimiento de [la privacidad electrónica de AAM.](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * No se aceptan otros valores para este parámetro

### DMP

* Datos de contexto: `contextData.['opt.dmp']`
* Valores aceptados:
   * `N` - Al enviar el valor `N`, esto indica que el consumidor está optando por no compartirlo en las plataformas de administración de datos. Tenga en cuenta que no se comparte el bloqueo actual con AAM.  Utilice SSF para esa funcionalidad.
   * `Y` - Al enviar el valor `Y`, esto indica que el consumidor está optando por compartir datos en plataformas de administración de datos.

### VENDER

* Datos de contexto: `contextData.['opt.sell']`
* Valores aceptados:
   * `N` - Al enviar el valor `N`, esto indica que el consumidor está optando por no compartir o vender los datos a terceros.
   * `Y` - Al enviar el valor `Y`, esto indica que el consumidor está optando por compartir o vender los datos a terceros.
