---
description: Explica la nueva estrategia de lanzamiento continuo de funcionalidades para Adobe Analytics
title: Versiones de funcionalidades de Adobe Analytics
translation-type: ht
source-git-commit: bbbe6dccfee81ae5111f295906aa3a23d68ad39e
workflow-type: ht
source-wordcount: '422'
ht-degree: 100%

---


# Versiones de funcionalidades de Adobe Analytics

Históricamente, las versiones de funcionalidades de Adobe Analytics seguían un calendario mensual fijo. Desde abril de 2020, Adobe Analytics se trasladó a un modelo de envío continuo que permite un enfoque más escalable y gradual de la implementación de funcionalidades.

## Estrategia de lanzamiento

[!UICONTROL Analysis Workspace] utiliza indicadores de funcionalidades (también conocidos como “alternadores”) para controlar la visibilidad de las nuevas funcionalidades, lo que permite realizar pruebas de escala controladas antes del lanzamiento final. Esta estrategia de versión incluye las siguientes fases:

* **Versión para producción (RTP)**: El código se libera para su producción, con la visibilidad de las funcionalidades desactivada en Analysis Workspace. **Nota**: En RTP, la función puede estar disponible en la API de Analytics 2.0.

* **Prueba limitada**: Una versión por fases comienza con las pruebas realizadas por los usuarios internos de Adobe. La versión se escalará de 0% a 100% de disponibilidad en un par de meses. La implementación por fases se produce en el nivel de organización de Experience Cloud, por lo que todos los usuarios con derecho de una organización reciben la misma experiencia.

* **Disponibilidad general (GA)**: La funcionalidad está disponible para el 100% de las organizaciones de Experience Cloud y la versión de la funcionalidad está completa.

Con cada versión de la funcionalidad, los plazos desde la fase de producción hasta su disponibilidad general pueden variar. El objetivo es reducir el número de versiones, de modo que en los 2 meses posteriores al comienzo de la producción, la funcionalidad esté disponible de forma general.

## Indicadores de características

Los indicadores de características se utilizan para controlar la visibilidad de las nuevas funciones durante el lanzamiento. Adobe recomienda añadir app.launchdarkly.com a la [lista de permitidos](https://docs.adobe.com/content/help/es-ES/analytics/technotes/ip-addresses.html) del cortafuegos para disfrutar de una experiencia óptima durante el lanzamiento. Poco después de que se llegue a GA, se elimina el indicador.

Puede realizar la vista de los indicadores de funciones activas en cualquier momento en **Ayuda > Acerca de Workspace > Indicadores** de funciones activas.

## Beneficios

Las versiones por fases permiten a Adobe escalar mejor el proceso de implementación de software y garantizar que las funcionalidades se desarrollen completamente antes de estar disponibles de forma general. También permite que las funcionalidades se publiquen tan pronto como estén disponibles, en lugar de seguir una tiempo de versión mensual fijo.

## Preguntas frecuentes

| Pregunta | Respuesta |
|---|---|
| ¿Puedo solicitar acceso anticipado a una funcionalidad? | No. No se puede solicitar el acceso anticipado.<br>Si desea probar las versiones iniciales de Analytics, le recomendamos que pruebe [Adobe Analytics Labs](https://docs.adobe.com/content/help/es-ES/analytics/analyze/tech-previews/overview.html) para proporcionar comentarios sobre las innovaciones líderes del sector. |
| ¿Esta estrategia de lanzamiento afecta mi acceso a las funcionalidades? | No. Una vez que una funcionalidad haya llegado a su fase de disponibilidad general, tendrá acceso a ella si está incluida en su paquete de Analytics.<br>Puede ver los detalles del paquete de Analytics en [!UICONTROL Administración] > [!UICONTROL Configuración de compañía] > [Niveles de acceso a funcionalidades](https://docs.adobe.com/content/help/es-ES/analytics/admin/company-settings/feature-access-levels.html). |
