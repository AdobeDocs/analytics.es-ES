---
description: AJAX es un concepto de nueva aparición en el diseño de contenido web que usa varias tecnologías para crear y administrar el contenido dinámico de las páginas web.
keywords: Implementación de Analytics
seo-description: AJAX es un concepto de nueva aparición en el diseño de contenido web que usa varias tecnologías para crear y administrar el contenido dinámico de las páginas web.
seo-title: Aplicaciones de medios enriquecidos de AJAX-Track
solution: Analytics
title: Aplicaciones de medios enriquecidos de AJAX-Track
topic: Desarrollador e implementación
uuid: ffe 6 a 263-ae 18-4875-badb-b 3 aea 3 efcb 64
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aplicaciones de medios enriquecidos de AJAX-Track

AJAX es un concepto de nueva aparición en el diseño de contenido web que usa varias tecnologías para crear y administrar el contenido dinámico de las páginas web.

La necesidad de realizar un seguimiento de la interacción del usuario con [!UICONTROL AJAX] y otras aplicaciones multimedia enriquecidas es crucial para el éxito de los análisis y para materializar el retorno de la inversión realizada en el diseño de contenido web. El objetivo de este documento es proporcionar recomendaciones para realizar el seguimiento de aplicaciones de Internet enriquecidas, específicamente aquellas que usan [!UICONTROL AJAX].

## Aplicaciones de Internet enriquecidas (RIA) {#section_CDCAFC4E05B44985BCBF34DFCB35DCA6}

Las aplicaciones de Internet enriquecidas (RIA) están cambiando la cara de la web. Tienden un puente entre la promesa de tecnologías a demanda para el gran público y las experiencias del usuario realistas. Las RIA han madurado durante años. El gran salto se ha producido con la adopción a gran escala de los exploradores, que admiten las tecnologías subyacentes que alimentan estas aplicaciones. Aunque las RIA tienen muchas formas y tecnologías compatibles, las más comunes, y quizás las más utilizadas, son AJAX y Flash. Es importante comprender que la tecnología no es lo que define una RIA, sino su capacidad de uso y aplicación.

## Qué seguir {#section_E96EC5127E554B8384FD0A7A0B3118DF}

Una de las preguntas que más se plantea con las RIA es cómo seguir la actividad de micronivel independientemente de la actividad de macronivel, y cuándo es apropiado utilizar una u otra. Por ejemplo, supongamos que tiene una aplicación que permite a los clientes configurar un producto de forma única. La aplicación podría tener pasos importantes a los que se exponen los usuarios. ¿Estos pasos se consideran vistas de página? Además, hay actividades de micronivel dentro de cada paso. ¿Estas actividades deben seguirse como vistas de página?

¿Y si quiere comprender el flujo entre las actividades o qué funciones presentan la mayor actividad? El problema de las RIA es que cada aplicación es única. Están diseñadas para simular acciones realistas y como estas acciones son relativas a la situación, las posibilidades son innumerables. Sin embargo, la mayoría de las aplicaciones tienen algunos componentes principales: pasos del hito, funciones y acciones de micronivel dentro de las funciones. Por lo tanto, aunque para cada aplicación es necesario considerar qué se debe medir específicamente, se pueden aplicar algunas generalizaciones al seguimiento de RIA.
La actividad de macronivel suele constituir la carga de la aplicación. Proporciona información sobre visitas, visitantes, instancias, valor para futuras acciones, etc. También puede, y debe, representar los principales pasos del proceso. Una buena regla general es que si una acción de la RIA cambia la aplicación más del 50 % (o el porcentaje que se considere que cambia significativamente la experiencia del usuario o el contenido), se trata de una actividad de macronivel y debe seguirse como una vista de página.
La actividad de micronivel incluye cambios inferiores al 50 % (o que no se considera que cambien significativamente la experiencia del usuario o el contenido). Alternar entre opciones de color, por ejemplo, se consideraría una actividad de micronivel. Adobe recomienda que el seguimiento de la actividad de micronivel esté relacionado con las funciones. Por ejemplo, en el caso de los cambios de color, ¿es realmente importante comprender qué colores se tuvieron en cuenta? ¿O es más importante saber que se usó la función de selección de color? Quizás ambas sean importantes; si es así, capture ambas pero a la hora de medir la efectividad de la RIA, considere que la actividad en el nivel de la función es más valiosa.

Toda la actividad de micronivel debe seguirse como vínculos personalizados con especificaciones medidas con variables de tráfico asociadas (props y eVars si es necesario medir el uso respecto a eventos de éxito). Esto garantiza que las vistas de página no aumentan debido a la actividad de micronivel y permite realizar el análisis de rutas mediante la variable de tráfico.

## Qué analizar {#section_56824EF675874BA99127A566F6B1383F}

Es importante comprender si su RIA está contribuyendo al éxito de forma efectiva. Normalmente, el éxito se mide mediante conversiones. Un análisis de macronivel proporciona información sobre la efectividad de la RIA en su conjunto. Los análisis de micronivel pueden proporcionar información sobre qué características ayudan a realizar la conversión.

Ahora debe medir la eficiencia de su RIA. Este es un análisis de la actividad de micronivel con relación a las métricas de la actividad de macronivel de la RIA. ¿Los usuarios recorren más pasos de los necesarios para llegar al mismo objetivo? Las métricas de análisis podrían incluir las actividades visitas/función, vistas de página/función, visitantes/función, etc.

Realice análisis del flujo de rutas y visitas en el orden previsto. ¿Los usuarios están evitando la RIA y buscan otra ruta hacia el objetivo? Ejecute los informes de visitas en el orden previsto para el sitio y el flujo de la RIA. Ejecute análisis de rutas desde las páginas de aterrizaje para evaluar los patrones de tráfico reales. Busque barreras e incentivos para guiar a los usuarios hacia el objetivo.

## Métricas sugeridas {#section_AB7047D6C74740C6B6E47ED93602DB07}

* Visitas a la RIA
* Visitantes de la RIA
* Vistas de páginas de la RIA
* Actividad de las funciones de la RIA (vínculos personalizados); miden la actividad de clic por función

## Análisis sugeridos {#section_5BE0FB9ECA3049E5965BEAD733DA5B6E}

* Actividad de las funciones de la RIA / Vistas de páginas de la RIA
* Actividad de las funciones de la RIA / Visitas a la RIA -
* Vistas de páginas de la RIA / Métrica de éxito - Cociente de conversión: mide la efectividad de la aplicación
* Actividad total de la RIA / Métrica de éxito - Cociente de conversión: mide la eficiencia de la aplicación
* Actividad de las funciones de la RIA / Métrica de éxito - Cociente de conversión: mide la eficiencia de la aplicación
* Flujo de rutas hacia y desde la RIA
* Tasas de visitas en el orden previsto mediante conversión de la RIA

