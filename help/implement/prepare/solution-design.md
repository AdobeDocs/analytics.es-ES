---
title: Creación de un documento de diseño de solución
description: Descubra qué es un documento de diseño de solución y cómo puede utilizarlo en su organización.
exl-id: 0b5c5ddd-5f53-4790-a649-1381135dacda
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '696'
ht-degree: 100%

---

# Creación de un documento de diseño de solución

Un documento de diseño de solución (también conocido como referencia de diseño de solución o documento de requisitos comerciales) es, en esencia, el modelo de implementación de Analytics. Define criterios identificados por los interesados en toda la organización y los traduce a variables dentro de Adobe Analytics. Sin una, las organizaciones tienen dificultades para coordinar las necesidades de presentación de informes y tienden a dejar de reunir datos importantes.

## Requisitos previos

[Valide la implementación de Analytics y envíe informes a producción](../launch/validate-publish-prod.md). Aunque no es necesario directamente, Adobe recomienda disponer de una implementación básica para recopilar datos críticos mientras se establecen e implementan requisitos comerciales adicionales.

## Propiedad y ubicación del documento de diseño

* **Determine quién será el responsable de mantener el documento de diseño de la solución de su organización.** Esta función puede ser individual o de equipo. Asegúrese de que el mantenimiento del diseño de la solución se conserva incluso mediante cambios de funciones o reestructuras de la organización. Es un documento vivo y debe mantenerse adecuadamente.
* **Determine dónde residirá el documento de la solución.** No hay lugar recomendado para que residan los documentos de diseño de soluciones, pero normalmente se conservan en una ubicación interna a la que puedan acceder los usuarios. Algunos ejemplos son una hoja de cálculo compartida o un espacio de trabajo colaborativo como SharePoint o una wiki interna. No es necesario que sea editable para todos, pero es beneficioso para aquellos que pueden acceder a los informes al menos poder verlo.

## Definir los requisitos comerciales

Al determinar qué datos recopilar, es fácil decir “todo”; sin embargo, esto podría resultar difícil de administrar e incluso puede proporcionar menos en comparación con recopilaciones más concisas de datos.

1. **Determine los indicadores de rendimiento clave.** ¿Qué desea que hagan los visitantes en última instancia? La respuesta a esta pregunta varía según la industria y el sector. Los ejemplos incluyen compras, registros o clics en publicidad.
1. **Averiguar los datos más importantes para recopilarlos.** Haga preguntas comerciales a las que desee respuestas específicas. Las respuestas a estas preguntas le proporcionarán información sobre cómo mejorar los KPI.
1. **Tome esas preguntas y determine cuáles son sus necesidades de seguimiento.** Agrúpelas en dimensiones y métricas.
   * Las dimensiones son variables que contienen texto. Algunos ejemplos son el término de búsqueda interna, la categoría del producto o el nombre del área en la que hizo clic un visitante.
   * Las métricas son eventos específicos que desea que realice un visitante: cuando lo haga, el número aumentará en uno. Algunos ejemplos son el envío de un pedido, la suscripción a un boletín o el envío de una respuesta a una encuesta.
1. **Asigne dimensiones y métricas a una página o hoja de cálculo.** Esta página o tabla se convierte finalmente en el documento de diseño de la solución. Algunas columnas útiles o puntos de viñeta que se pueden incluir:
   * Estado de implementación: Planificado, activo, inactivo, fallido, etc. Esto informaría a los visualizadores del documento sobre el estado de la variable, si se ha implementado o si hay problemas con la recopilación de datos.
   * Nombre de variable: “Términos de búsqueda interna”, por ejemplo. Este valor es lo que los analistas verán al trabajar con Analytics.
   * Variable de Analytics asignada: A qué variable predeterminada o personalizada de Analytics elige asignar valores. Las dimensiones normalmente caen dentro de las eVars, mientras que las métricas caen dentro de los eventos.
   * Lógica: Descripción de cómo se establece la variable y qué determina su valor. Por ejemplo: “Solo se configura en páginas de búsqueda interna. Toma el valor del parámetro de cadena de consulta q”.
   * Cualquier otra nota que desee incluir en relación con la variable.

## Recursos adicionales

La definición de un documento de diseño de solución es un proyecto bastante complejo, especialmente para las organizaciones que no lo han creado anteriormente. Si necesita asistencia adicional, Adobe proporciona asesoramiento especializado para ayudarle a poner en marcha su organización con Adobe Analytics. Póngase en contacto con el Administrador de cuentas si desea obtener los servicios profesionales de Adobe. Se puede rellenar un [cuestionario técnico previo a la implementación](assets/technical-pre-implementation-questionnaire.pdf) para que Adobe sepa exactamente cómo ayudarle en función de las necesidades de su organización.

También hay varios socios de Adobe que se especializan en ayudar a crear un documento de diseño de solución, así como en implementar Adobe Analytics en su sitio.

## Pasos siguientes

Implemente las variables en el documento de diseño de la solución.

[Crear una capa de datos](data-layer.md): traduzca las variables de su documento de diseño a las variables JavaScript de su sitio.
