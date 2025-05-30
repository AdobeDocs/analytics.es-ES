---
description: En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.
title: Flujo de trabajo del generador de reglas de clasificación
feature: Classifications
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 86%

---

# Resumen del generador de reglas de clasificación (heredado)

En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. Las reglas se procesan a intervalos frecuentes, según el volumen de tráfico relacionado con la clasificación.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Generador de reglas de clasificación](https://video.tv.adobe.com/v/3434377?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

## Aviso importante antes de comenzar

Tenga en cuenta estos puntos al utilizar reglas de clasificación:

* Puede exportar hasta 10 millones de filas a la vez.
* Cuando CRB solicita una exportación, extrae valores clasificados y no clasificados, con valores no clasificados que llegan al final de la exportación. Esto significa que, con el tiempo, se podrían completar 10 millones de valores clasificados - sin llegar nunca a los valores no clasificados.
* Debido a que la arquitectura está configurada de manera que CRB podría estar extrayendo del número “n” de servidores, esto puede generar incoherencias en cuanto a los servidores que se recogen y en qué orden. Por esa razón, es muy difícil llegar a valores no clasificados.

Esta es la **solución** para aquellos que tienen más de 10 millones de valores clasificados para una dimensión: Deberá exportar valores no clasificados mediante FTP, en lotes de 10 millones de lotes y clasificarlos manualmente.

## Introducción a Reglas de clasificación {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administración]** > **[!UICONTROL Clasificación del Generador de reglas]**

Instrucciones avanzadas relacionadas con la implementación de reglas de clasificación:

| Paso | Dónde se realiza | Descripción |
|--- |--- |--- |
| Paso 1 (requisito previo): Configure el esquema de clasificación. | [!UICONTROL Administrador] > [!UICONTROL Grupos de informes] > [!UICONTROL Editar configuración] > [!UICONTROL Clasificaciones de tráfico] o [!UICONTROL Clasificaciones de conversión] | Permite elegir una variable y definir las clasificaciones que se usarán para esa variable. <br>Para poder utilizar las variables en las reglas, debe haberse creado en ellas una columna de clasificación como mínimo.<br>Una vez que se habiliten las clasificaciones, se puede usar el importador y el generador de reglas para clasificar valores específicos. |
| Paso 2: [Crear un conjunto de reglas](classification-rule-set.md). | [!UICONTROL Administración] > [!UICONTROL Clasificación del Generador de reglas] > [!UICONTROL Agregar conjunto de reglas] | Un conjunto de reglas es un grupo de reglas de clasificación para una variable específica. |
| Paso 3: Configurar grupo de informes y variables. | [!UICONTROL Clasificación del Generador de reglas] >  &lt;su conjunto de reglas> | Permite aplicar el conjunto de reglas a grupos de informes y variables. |
| Paso 4: [Agregar reglas de clasificación al conjunto](classification-quickstart-rules.md). | [!UICONTROL Clasificación del Generador de reglas] >  &lt;su conjunto de reglas> | Hacer coincidir una condición con una clasificación y especificar la acción que debe realizarse con la regla.  Familiarícese con la información en [Cómo procesarlas reglas](classification-quickstart-rules.md). |
| Paso 5: [Probar un conjunto de reglas de clasificación](classification-quickstart-rules.md) | [!DNL Testing Page] | Para probar las reglas antes de su validación, deben editarse en modo borrador. En este modo, las reglas no pueden ejecutarse.<br>Este paso es importante cuando se utilizan [expresiones regulares](classification-quickstart-rules.md). |
| Paso 6: [Activar reglas válidas](classification-rule-definitions.md). | [!DNL Rules Page] | Cuando las reglas se definen como válidas se puede activar el conjunto de reglas.  Si se considera necesario, pueden sobrescribirse las claves existentes. Ver [Cómo procesar las reglas](classification-quickstart-rules.md). |
| Paso 7 (opcional): [Eliminar las reglas no deseadas](classification-rule-definitions.md). | [!DNL Rules Page] | Eliminar las reglas no deseadas de un conjunto.<br>Nota: al eliminar las reglas, no se eliminan los datos clasificados que se han cargado. Consulte [Eliminar datos de clasificación](/help/components/classifications/importer/t-delete-classification-data.md) si necesita eliminar datos clasificados. |

>[!NOTE]
>
>Los grupos con permisos para utilizar la herramienta para importar clasificaciones también pueden utilizar las reglas de clasificación. Consulte [Procesamiento de reglas](classification-quickstart-rules.md) para obtener información importante acerca del procesamiento.

**Recursos adicionales**

**Blog**: Para obtener más información sobre esta característica, consulte el Blog de Digital Marketing - [Clasificaciones basadas en reglas](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Vídeo**: Vea el vídeo [Descripción general de las clasificaciones](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/classifications/overview-of-classifications.html?lang=es).
