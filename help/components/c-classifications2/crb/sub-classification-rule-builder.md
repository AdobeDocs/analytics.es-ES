---
description: Puede combinar el Generador de reglas de clasificaciones con subclasificaciones para simplificar la administración de clasificaciones y reducir el número de reglas necesarias. Puede ser conveniente hacer esto si el código de seguimiento está formado por códigos que desea clasificar de forma independiente.
subtopic: Classifications
title: 'Subclasificaciones y el Generador de reglas: Caso de uso'
topic: Admin tools
uuid: 6db6a4a9-b93c-413b-8049-1e6cc1ba4a38
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Subclasificaciones y el Generador de reglas: Caso de uso

Puede combinar el Generador de reglas de clasificaciones con subclasificaciones para simplificar la administración de clasificaciones y reducir el número de reglas necesarias. Puede ser conveniente hacer esto si el código de seguimiento está formado por códigos que desea clasificar de forma independiente.

## Subclasificaciones y el Generador de reglas: Caso de uso {#concept_6C8672C242544D7487E82886BBFABE6E}

Puede combinar el Generador de reglas de clasificaciones con subclasificaciones para simplificar la administración de clasificaciones y reducir el número de reglas necesarias. Puede ser conveniente hacer esto si el código de seguimiento está formado por códigos que desea clasificar de forma independiente.

Consulte [Subclasificaciones](/help/components/c-classifications2/c-sub-classifications.md) para obtener información conceptual sobre las subclasificaciones.

**Ejemplo**

Supongamos que tenemos el siguiente código de seguimiento:

`channel:broad_campaign:creative`

Las jerarquías de clasificación permiten aplicar una clasificación a otra (llamada *`sub-classification`*). Es decir, puede usar el importador como si fuera una base de datos relacional con varias tablas. Una tabla asigna los códigos de seguimiento completos a claves y otra asigna esas claves a otras tablas.

![](assets/sub_class_table.png)

Una vez preparada esta estructura, puede usar el  [Generador de reglas de clasificaciones](/help/components/c-classifications2/crb/classification-rule-builder.md) para cargar archivos pequeños que solo actualicen las tablas de búsqueda (las tablas verde y roja de la imagen anterior). A continuación, puede usar el Generador de reglas para mantener actualizada la tabla de la clasificación principal.

En la siguiente tarea, se describe cómo hacerlo.

## Configurar subclasificaciones mediante el Generador de reglas {#task_2D9016D8B4E84DBDAF88555E5369546F}

<!-- 

t_rule_builder_subclass.xml

 -->

Ejemplo paso por paso que describe cómo cargar subclasificaciones mediante el Generador de reglas.

>[!NOTE]
>
>Estos pasos describen cómo se lleva a cabo el caso de uso descrito en [Subclasificaciones y el Generador de reglas](/help/components/c-classifications2/crb/sub-classification-rule-builder.md).

1. Cree clasificaciones y subclasificaciones en el [Administrador de clasificación](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html).

   Ejemplo:

   ![Información sobre los pasos](assets/sub_class_create.png)

1. En el [Generador de reglas de clasificación](/help/components/c-classifications2/crb/classification-rule-builder.md), clasifique la clave de subclasificación del código de seguimiento original.

   Para hacerlo, se usa una expresión regular. En este ejemplo, la regla para rellenar el  *`Broad Campaign code`* utilizaría esta expresión regular:

   | `#` | Tipo de regla | Coincidencias | Configurar clasificación | Hasta |
   |---|---|---|---|---|
   |  | Expresión regular | `[^\:]:([^\:]):([^\:]`) | código Campaña general | `$1` |
   |  | Expresión regular | `[^\:]:([^\:]):([^\:]`) | código Creativo | `$2` |

   >[!NOTE]
   >
   >En este momento, no se rellenan las subclasificaciones *`Campaign Type`* ni *`Campaign Director`*.

1. Cargue un archivo de clasificación que incluya solamente las subclasificaciones especificadas.

   Consulte [Clasificaciones de varios niveles](/help/components/c-classifications2/c-sub-classifications.md).

   Ejemplo:

   | Clave | Canal | código Campaña general | Campaña amplia, código&amp;Sombrero;Tipo de campaña | Campaña amplia de código&amp;Sombrero;Director de campaña | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | Marca | Suzanne |  |
   | * |  | 222 | Marca | Frank |  |

1. Para realizar el mantenimiento de las tablas de búsqueda, cargue un archivo pequeño (como se muestra arriba).

   Por ejemplo, cargaría este archivo cuando se introdujera un nuevo *`Broad Campaign code`*. Este archivo se aplicaría a los valores clasificados previamente. Del mismo modo, si crea una nueva subclasificación (por ejemplo,  *`Creative Theme`* como subclasificación de *`Creative code`*), solo se carga el archivo de subclasificación, en lugar de todo el archivo de clasificación.

   Por lo que respecta a los informes, estas subclasificaciones funcionan exactamente igual que las clasificaciones de nivel superior. De este modo, se reduce la carga administrativa necesaria para usarlas.
