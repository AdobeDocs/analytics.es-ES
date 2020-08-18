---
description: En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.
subtopic: Classifications
title: Flujo de trabajo del generador de reglas de clasificación
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 100%

---


# Flujo de trabajo del generador de reglas de clasificación

En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.

## Aviso importante antes de comenzar

Tenga esto en cuenta antes de empezar a utilizar reglas de clasificación:

* Las subclasificaciones no son compatibles con el Generador de reglas de clasificación (CRB).
* Nuestro sistema de clasificación actual solo puede exportar hasta 10 millones de filas a la vez.
* Cuando CRB solicita una exportación, extrae valores clasificados y no clasificados, con valores no clasificados que llegan al final de la exportación. Esto significa que, con el tiempo, se podrían completar 10 millones de valores clasificados - sin llegar nunca a los valores no clasificados.
* Debido a que la arquitectura está configurada de manera que CRB podría estar extrayendo del número “n” de servidores, esto puede generar incoherencias en cuanto a los servidores que se recogen y en qué orden. Por esa razón, es muy difícil llegar a valores no clasificados.

Esta es la **solución** para aquellos que tienen más de 10 millones de valores clasificados para una dimensión: Deberá exportar valores no clasificados mediante FTP, en lotes de 10 millones de lotes y clasificarlos manualmente.

## Introducción a Reglas de clasificación {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administración]** > **[!UICONTROL Clasificación del Generador de reglas]**

Instrucciones avanzadas relacionadas con la implementación de reglas de clasificación:

| Paso | Dónde se realiza | Descripción |
|--- |--- |--- |
| Paso 1 (requisito previo): [Configure el esquema de clasificación](https://docs.adobe.com/content/help/es-ES/analytics/components/classifications/c-classifications.html). | [!UICONTROL Administración] > Grupos [!UICONTROL de informes] > [!UICONTROL Editar configuración] > &lt;Clasificaciones de tráfico o Clasificaciones de conversión> | Permite elegir una variable y definir las clasificaciones que se usarán para esa variable. <br>Para poder utilizar las variables en las reglas, debe haberse creado en ellas una columna de clasificación como mínimo.<br>Una vez que se habiliten las clasificaciones, se puede usar el importador y el generador de reglas para clasificar valores específicos. |
| Paso 2: [Crear un conjunto de reglas](/help/components/classifications/crb/classification-rule-set.md). | [!UICONTROL Administración] > [!UICONTROL Clasificación del Generador de reglas] > [!UICONTROL Agregar conjunto de reglas] | Un conjunto de reglas es un grupo de reglas de clasificación para una variable específica. |
| Paso 3: Configurar grupo de informes y variables. | [!UICONTROL Clasificación del Generador de reglas] >  &lt;su conjunto de reglas> | Permite aplicar el conjunto de reglas a grupos de informes y variables. |
| Paso 4: [Agregar reglas de clasificación al conjunto](/help/components/classifications/crb/classification-quickstart-rules.md). | [!UICONTROL Clasificación del Generador de reglas] >  &lt;su conjunto de reglas> | Hacer coincidir una condición con una clasificación y especificar la acción que debe realizarse con la regla.  Familiarícese con la información en [Cómo procesarlas reglas](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Paso 5: [Probar un conjunto de reglas de clasificación](/help/components/classifications/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Para probar las reglas antes de su validación, deben editarse en modo borrador. En este modo, las reglas no pueden ejecutarse.<br>Este paso es importante cuando se utilizan [expresiones regulares](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Paso 6: [Activar reglas válidas](/help/components/classifications/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Cuando las reglas se definen como válidas se puede activar el conjunto de reglas.  Si se considera necesario, pueden sobrescribirse las claves existentes. Consulte [Cómo procesar las reglas](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Paso 7 (opcional): [Eliminar las reglas no deseadas](/help/components/classifications/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Eliminar las reglas no deseadas de un conjunto.<br>Nota: Al eliminar las reglas, no se eliminan los datos clasificados que se han cargado.  Consulte [Eliminar datos de clasificación](/help/components/classifications/importer/t-delete-classification-data.md) para eliminar datos clasificados. |

>[!NOTE]
>
>Los grupos con permisos para utilizar la herramienta para importar clasificaciones también pueden utilizar las reglas de clasificación. Consulte [Procesamiento de reglas](/help/components/classifications/crb/classification-quickstart-rules.md) para obtener información importante acerca del procesamiento.

**Recursos adicionales**

**Blog**: Para obtener más información sobre esta característica, consulte el Blog de Digital Marketing - [Clasificaciones basadas en reglas](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Vídeo**: Visite [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) para ver el vídeo [!UICONTROL Resumen general de las clasificaciones].
