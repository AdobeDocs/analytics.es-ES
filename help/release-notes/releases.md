---
description: Explica la estrategia de lanzamiento continuo de funcionalidades para Adobe Analytics
title: Versiones de funcionalidades de Adobe Analytics
feature: Release Notes
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---

# Versiones de funcionalidades de Adobe Analytics

Las versiones de Adobe Analytics funcionan con un modelo de entrega continuo que permite un enfoque más escalable y gradual de la implementación de funcionalidades.

## Estrategia de lanzamiento

[!UICONTROL Analysis Workspace] utiliza indicadores de funcionalidades (también conocidos como “conmutadores”) para controlar la visibilidad de las nuevas funcionalidades, lo que permite realizar pruebas de escala controladas antes del lanzamiento final. Esta estrategia de versión incluye las siguientes fases:

* **Prueba limitada**: una versión por fases comienza con las pruebas realizadas por los usuarios internos de Adobe. A continuación, se pone a disposición de un pequeño grupo de cuentas del cliente para garantizar que la funcionalidad satisfaga sus necesidades y expectativas.

* **Inicio del despliegue**: el despliegue de una versión por fases comienza con la prueba limitada. Después, la versión se escalará con una disponibilidad del 0 % al 100 % en el transcurso de un par de meses. La implementación por fases se produce en el nivel de organización de Experience Cloud, por lo que todos los usuarios con derecho de una organización reciben la misma experiencia.

* **Disponibilidad general (GA)**: la funcionalidad está disponible para el 100% de las organizaciones de Experience Cloud y la versión de la funcionalidad está completa.

Con cada versión de la funcionalidad, la cronología desde el inicio del despliegue hasta su disponibilidad general puede variar. El objetivo es reducir el número de versiones, de modo que, en los dos meses posteriores al inicio del despliegue, la funcionalidad esté disponible de forma general.

## Indicadores de características

Los indicadores de características se utilizan para controlar la visibilidad de las nuevas funciones durante el lanzamiento. Adobe recomienda añadir `app.launchdarkly.com` a la [lista de permitidos](/help/technotes/ip-addresses.md) del cortafuegos para disfrutar de una experiencia óptima durante el lanzamiento. Poco después de que se llegue a GA, se elimina el indicador.

Puede realizar la vista de los indicadores de funciones activas en cualquier momento en **Ayuda > Acerca de Espacio de trabajo > Indicadores de funciones activas**.

## Beneficios

Las versiones por fases permiten a Adobe escalar mejor el proceso de implementación de software y garantizar que las funcionalidades se desarrollen completamente antes de estar disponibles de forma general. También permite que las funcionalidades se publiquen tan pronto como estén disponibles, en lugar de seguir una tiempo de versión mensual fijo.

## Preguntas frecuentes

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo solicitar acceso anticipado a una funcionalidad? | No. No se puede solicitar el acceso anticipado.<br>Si desea probar las versiones iniciales de Analytics, le recomendamos que pruebe [Adobe Analytics Labs](/help/analyze/labs.md) para proporcionar comentarios sobre las innovaciones líderes del sector. |
| ¿Esta estrategia de lanzamiento afecta mi acceso a las funcionalidades? | No. Una vez que una funcionalidad haya llegado a su fase de disponibilidad general, tendrá acceso a ella si está incluida en su paquete de Analytics.<br>Puede ver los detalles del paquete de Analytics en [Niveles de acceso de las funciones](/help/admin/tools/company/feature-access-levels.md). |
