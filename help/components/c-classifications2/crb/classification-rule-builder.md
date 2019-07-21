---
description: En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.
seo-description: En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.
seo-title: Flujo de trabajo del Generador de reglas de clasificación
solution: Analytics
subtopic: Clasificaciones
title: Flujo de trabajo del Generador de reglas de clasificación
topic: Herramientas de administración
uuid: edb 1 f 07 e-fa 86-4055-8 f 4 b-cce 2 d 370 edbb
translation-type: tm+mt
source-git-commit: e71c24fa4762d7f0bc80fc7133ca1cd79dfaf7c5

---


# Flujo de trabajo del Generador de reglas de clasificación

En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.

## Aviso importante antes de comenzar

Tenga en cuenta esto antes de empezar a utilizar reglas de clasificación:

* Nuestro sistema de clasificación actual sólo puede exportar hasta 10 millones de filas a la vez.
* Cuando el generador de reglas de clasificación (CRB) solicita una exportación, extrae ambos valores clasificados y sin clasificar, con valores sin clasificar que llegan al final de la exportación. Esto significa que, a lo largo del tiempo, podría llenar 10 millones de valores clasificados, sin llegar nunca a los valores sin clasificar.
* Debido a que la arquitectura está configurada de manera tal que CRB pueda extraer del número "n" de servidores, esto puede llevar a incoherencias en cuanto a los servidores que se obtienen y en qué orden. Por este motivo, es muy difícil obtener valores sin clasificar.

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## Introducción a Reglas de clasificación {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administración]** &gt; **[!UICONTROL Clasificación Generador de reglas]**

Estos son los pasos de alto nivel que se toman para implementar las reglas de clasificación:

| Paso | Dónde se realiza | Descripción |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications). | [!UICONTROL Administración] &gt; [!UICONTROL Grupos] de informes &gt; [!UICONTROL Editar configuración] &gt; &lt; Clasificaciones de tráfico o Clasificaciones de conversión &gt; | Permite elegir una variable y definir las clasificaciones que se usarán para esa variable. <br>Para poder utilizar las variables en las reglas, debe haberse creado en ellas una columna de clasificación como mínimo.<br>Una vez que se habiliten las clasificaciones, se puede usar el importador y el generador de reglas para clasificar valores específicos. |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Administración] &gt; [!UICONTROL Clasificación del Generador de reglas] &gt; [!UICONTROL Agregar conjunto de reglas] | Un conjunto de reglas es un grupo de reglas de clasificación para una variable específica. |
| Paso 3: Configure grupos de informes y variables. | [!UICONTROL Generador de reglas de clasificación] &gt; &lt; su conjunto de reglas &gt; | Permite aplicar el conjunto de reglas a grupos de informes y variables. |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Generador de reglas de clasificación] &gt; &lt; su conjunto de reglas &gt; | Hacer coincidir una condición con una clasificación y especificar la acción que debe realizarse con la regla.  Be familiar with the information in  [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Para probar las reglas antes de su validación, deben editarse en modo borrador. En este modo, las reglas no pueden ejecutarse.<br>Este paso es importante cuando se utilizan [expresiones regulares](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 6: [Activate valid rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Cuando las reglas se definen como válidas se puede activar el conjunto de reglas.  Si se considera necesario, pueden sobrescribirse las claves existentes. Consulte [Cómo procesar las reglas](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Eliminar las reglas no deseadas de un conjunto.<br>Nota: Al eliminar las reglas, no se eliminan los datos clasificados que se han cargado.  See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Los grupos con permisos para utilizar la herramienta de importación de clasificaciones pueden utilizar reglas de clasificación. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Recursos adicionales**

**Blog**: Para obtener más información sobre esta función, consulte el blog de Digital Marketing: [Clasificaciones basadas en reglas](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Vídeo**: Visite [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) para ver el vídeo [!UICONTROL Información general] sobre las clasificaciones.
