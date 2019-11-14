---
description: En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.
solution: Analytics
subtopic: Classifications
title: Flujo de trabajo del generador de reglas de clasificación
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Flujo de trabajo del generador de reglas de clasificación

En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.

## Aviso importante antes de comenzar

Tenga esto en cuenta antes de empezar a utilizar reglas de clasificación:

* Nuestro sistema de clasificación actual sólo puede exportar hasta 10 millones de filas a la vez.
* Cuando el creador de reglas de clasificación (CRB) solicita una exportación, extrae valores clasificados y no clasificados, con valores no clasificados que llegan al final de la exportación. Esto significa que, con el tiempo, se podrían completar 10 millones de valores clasificados - sin llegar nunca a los valores no clasificados.
* Debido a que la arquitectura está configurada de manera que CRB podría estar extrayendo del número "n" de servidores, esto puede generar incoherencias en cuanto a los servidores que se recogen y en qué orden. Por esa razón, es muy difícil llegar a valores no clasificados.

Esta es la **solución** para aquellos que tienen más de 10 millones de valores clasificados para una dimensión: Deberá exportar valores no clasificados mediante FTP, en lotes de 10 millones de lotes y clasificarlos manualmente.

## Introducción a Reglas de clasificación {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administración]** &gt; Generador de reglas **[!UICONTROL de clasificación]**

Estos son los pasos de alto nivel que debe realizar para implementar las reglas de clasificación:

| Paso | Dónde se realiza | Descripción |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Administración] &gt; Grupos [!UICONTROL de informes] &gt; [!UICONTROL Editar configuración] &gt; &lt;Clasificaciones de tráfico o Clasificaciones de conversión&gt; | Permite elegir una variable y definir las clasificaciones que se usarán para esa variable. <br>Para poder utilizar las variables en las reglas, debe haberse creado en ellas una columna de clasificación como mínimo.<br>Una vez que se habiliten las clasificaciones, se puede usar el importador y el generador de reglas para clasificar valores específicos. |
| Step 2: [Create a rule set](/help/components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Administración] &gt; [!UICONTROL Clasificación del Generador de reglas] &gt; [!UICONTROL Agregar conjunto de reglas] | Un conjunto de reglas es un grupo de reglas de clasificación para una variable específica. |
| Paso 3: Configure grupos de informes y variables. | [!UICONTROL Generador] de reglas de clasificación &gt; &lt;su conjunto de reglas&gt; | Permite aplicar el conjunto de reglas a grupos de informes y variables. |
| Step 4: [Add classification rules to the set](/help/components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Generador] de reglas de clasificación &gt; &lt;su conjunto de reglas&gt; | Hacer coincidir una condición con una clasificación y especificar la acción que debe realizarse con la regla.  Familiarícese con la información en [Cómo procesar](/help/components/c-classifications2/crb/classification-quickstart-rules.md)las reglas. |
| Step 5: [Test a Classification Rule Set](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Para probar las reglas antes de su validación, deben editarse en modo borrador. En este modo, las reglas no pueden ejecutarse.<br>Este paso es importante cuando se utilizan expresiones [regulares](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Paso 6: [Activar reglas](/help/components/c-classifications2/crb/classification-rule-definitions.md)válidas. | [!DNL Rules Page] | Cuando las reglas se definen como válidas se puede activar el conjunto de reglas.  Si se considera necesario, pueden sobrescribirse las claves existentes. Consulte [Cómo procesar las reglas](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Eliminar las reglas no deseadas de un conjunto.<br>Nota: Al eliminar las reglas, no se eliminan los datos clasificados que se han cargado.  See  [Delete classification data](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Los grupos con permisos para utilizar la herramienta de importación de clasificaciones pueden utilizar reglas de clasificación. See [How Rules Are Processed](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Recursos adicionales**

**Blog**: Para obtener información adicional sobre esta función, consulte el blog de marketing digital: Clasificaciones [basadas en](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)reglas.

**Vídeo**: Visite [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) para ver el vídeo Información general [!UICONTROL de] clasificaciones.
