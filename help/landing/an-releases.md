---
description: Explica la nueva estrategia de lanzamiento continuo de funciones para Adobe Analytics
title: 'Adobe Analytics: estrategia de lanzamiento de funciones'
translation-type: tm+mt
source-git-commit: 0b00405e9e27a427a85b0f4a0d970671ada4aa67
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# Adobe Analytics: estrategia de lanzamiento de funciones

Históricamente, las versiones de funciones de Adobe Analytics seguían una programación mensual fija. A partir de abril de 2020, Adobe Analytics pasará a un modelo de envío continuo que permite un enfoque más escalable y gradual de la implementación de funciones.

## Estrategia de lanzamiento

[!UICONTROL Análisis Workspace] utiliza indicadores de características (también conocidos como &quot;toggles&quot;) para controlar la visibilidad de las nuevas funciones, lo que permite realizar pruebas de escala controladas antes de la versión completa. Esta estrategia de versión incluye las siguientes fases:

* **Versión a producción (RTP)**: El código se libera para su producción, con la visibilidad de las funciones desactivada en el espacio de trabajo de Análisis. **Nota**: En este momento, la función puede estar disponible en la API de Analytics 2.0.

* **Prueba** limitada: Una versión por fases comienza con las pruebas realizadas por los usuarios internos de Adobe. La versión se escalará de 0% a 100% de disponibilidad en un par de meses. La implementación por fases se produce en el nivel de organización de Experience Cloud, por lo que todos los usuarios con derecho en una organización reciben la misma experiencia.

* **Disponibilidad general (GA)**: La función está disponible para el 100 % de las organizaciones con licencia de Experience Cloud y la versión de las funciones se ha completado.

Con cada versión de función, la línea de tiempo desde RTP hasta GA puede variar. El objetivo es reducir el número de versiones, de modo que en los 2 meses posteriores al inicio de la versión (RTP), una función sea GA.

## Beneficios

Las versiones por fases permiten a Adobe escalar mejor el proceso de implementación de software y garantizar que las funciones se endurezcan completamente antes de la disponibilidad general. También permite que las funciones se publiquen tan pronto como estén disponibles, en lugar de seguir una ventana de versión mensual fija.

## Preguntas frecuentes

| Pregunta | Respuesta |
|---|---|
| ¿Puedo solicitar acceso anticipado a una función? | No. No se concederá el acceso anticipado.<br>Si desea probar conceptos iniciales de Analytics, le recomendamos que pruebe [Adobe Analytics Labs](https://docs.adobe.com/content/help/es-ES/analytics/analyze/tech-previews/overview.html) para proporcionar comentarios sobre nuestras innovaciones líderes en el sector. |
| ¿Esta estrategia de lanzamiento afecta mi acceso a las funciones? | No. Una vez que una función haya llegado a GA, tendrá acceso a la función si se incluye en el paquete de Analytics.<br>Puede vista de los detalles del paquete de Analytics en [!UICONTROL Administración] > Configuración [!UICONTROL de] Compañía > Niveles [de acceso a](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html)funciones. |