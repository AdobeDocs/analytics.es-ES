---
title: Creación de un documento de diseño de solución
seo-title: Creación de un documento de diseño de solución
description: Conozca qué es un documento de diseño de solución y cómo puede utilizarlo en su organización.
seo-description: Conozca qué es un documento de diseño de solución y cómo puede utilizarlo en su organización.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Creación de un documento de diseño de solución

Un documento de diseño de solución (también conocido como referencia de diseño de solución o documento de requisitos comerciales) es básicamente el modelo de la implementación de Analytics. Define los criterios identificados por las partes interesadas de toda la organización y los traduce a variables dentro de Adobe Analytics. Sin una, las organizaciones tienen un tiempo difícil de coordinar las necesidades de informes y tienden a perder datos importantes.

## Requisitos previos

[Validar la implementación de Analytics y publicar en producción](../implement-with-launch/validate-publish-prod.md) : Si bien no es necesario directamente, Adobe recomienda tener una implementación básica para que se recopilen los datos críticos mientras se establecen e implementan requisitos comerciales adicionales.

## Propiedad y ubicación del documento de diseño

* **Determinar qué personas de la organización serán responsables de mantener el documento de diseño de la solución.** Esta función puede ser un individuo o un equipo. Asegúrese de mantener el diseño de la solución, incluso mediante cambios de función u organización. Es un documento activo y debe mantenerse correctamente.
* **Determine dónde residirá el documento de la solución.** No existe un único lugar óptimo para que los documentos de diseño de la solución residirán, pero normalmente residen en una ubicación interna accesible. Algunos ejemplos son una hoja de cálculo compartida o un espacio de trabajo colaborativo como sharepoint o un wiki interno. No necesita ser editable para todos, pero resulta beneficioso para aquellos que pueden acceder a los informes al menos poder verlo.

## Defina los requisitos comerciales

Al determinar qué datos recopilarán, es fácil decir "todo", sin embargo, esto puede hacerse poco fácil de administrar e incluso puede proporcionar menos valores que recopilar cantidades más concisas de datos.

1. **Determine los indicadores de rendimiento clave.** ¿Qué desea que haga en definitiva los visitantes? La respuesta a esta pregunta varía según el sector y la vertical, y puede ser varias cosas. Algunos ejemplos son: compras, registros o clics en publicidad.
1. **Averiguar los datos más importantes que recopilar.** Formule preguntas comerciales a las que desee responder específicas. Las respuestas a estas preguntas proporcionan una visión detallada de cómo mejorar los KPI.
1. **Tome esas preguntas y determine cuáles son las necesidades de seguimiento.** Agruparlos en dimensiones y métricas.
   * Las dimensiones son variables que contienen texto. Algunos ejemplos serían el término de búsqueda interna, la categoría de productos o el nombre de un área donde el visitante hizo clic.
   * Las métricas son eventos específicos que desea que un visitante haga: cuando realizan una acción que desee, el número aumenta en uno. Algunos ejemplos serían enviar un pedido, suscribirse a un boletín informativo o enviar una respuesta de estudio.
1. **Asigne dimensiones y métricas a una página o hoja de cálculo.** En definitiva, esta página o tabla se convierte en el documento de diseño de la solución. Algunas columnas o puntos clave útiles para incluir:
   * Estado de implementación: Planeado, activo, inactivo, problemas, etc. Esto informará a los visores del documento del estado de la variable, si se ha implementado, o si hay problemas con la recopilación de datos.
   * Nombre de la variable: Por ejemplo, "Términos de búsqueda interna". Este valor sería lo que los analistas ven al trabajar en Analytics.
   * Variable de Analytics asignada a: Qué variable de Analytics predeterminada o personalizada elige asignar valores a. Las dimensiones suelen caer en evars, mientras que las métricas se incluyen en los eventos.
   * Lógica: Una descripción de cómo se establece la variable y lo que determina su valor. Por ejemplo: "Sólo se establece en páginas de búsqueda interna. Toma el valor del parámetro de cadena de consulta q. "
   * Cualquier otra nota que desee incluir en relación con la variable

## Recursos adicionales

La definición de un documento de diseño de solución es un proyecto bastante complejo, especialmente para organizaciones que no han creado una anteriormente. Si necesita ayuda adicional, Adobe proporciona asesoría especializada para ayudarle a poner en marcha su organización con Adobe Analytics. Póngase en contacto con el administrador de cuentas si desea enumerar los servicios profesionales de Adobe. A [Technical pre-implementation questionnaire](assets/technical-pre-implementation-questionnaire.pdf) can be filled out so Adobe knows exactly how to help based on your organization's needs.

También existen varios socios de Adobe que se especializan en ayudar a crear un documento de diseño de soluciones, además de implementar Adobe Analytics en su sitio.

> [!NOTE] Aunque los miembros de la comunidad de Analytics han encontrado los vínculos siguientes, no son propiedad de Adobe. Tenga en cuenta esta nota al ver su contenido.

* [7 Pasos para configurar el diseño de la solución de análisis de Web](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) por observepoint
* [Un esquema para el proceso de análisis digital](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) realizado por Analytics Demystified
* [La referencia de diseño de solución es realmente su BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) por análisis numérico
* [Cómo hacer que Antti Koski asigne mapa](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/) de etiquetado de Adobe Analytics
* [Importancia del documento de diseño de solución](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) por Ebiquity

## Pasos siguientes

Implemente las variables en el documento de diseño de la solución.

* Introducción a las evars: Averiguar qué es una evar, cómo funciona y cómo utilizar uno en la implementación
* Introducción a los eventos: Averiguar qué es un evento de éxito, cómo funciona y cómo utilizar uno en la implementación
