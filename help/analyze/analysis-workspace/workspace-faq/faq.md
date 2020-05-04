---
description: Preguntas más frecuentes sobre Workspace
title: Preguntas más frecuentes y resolución de problemas de Workspace
translation-type: tm+mt
source-git-commit: 7fbeac0488fbe9b3d10d7c1242f31250f1c7dc16

---


# Preguntas frecuentes

| Pregunta | Respuesta |
|--- |--- |
| ¿Cuáles son los requisitos previos para utilizar Análisis Workspace? | [Envío de datos a Adobe Analytics mediante Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): El uso de Analysis Workspace requiere una implementación activa. Compruebe que su organización está enviando datos a Adobe antes de utilizar la herramienta. Otras implementaciones, como DTM o las implementaciones manuales heredadas, también pueden funcionar. |
| ¿Cuáles son los requisitos de administración y acceso de Analysis Workspace? | Consulte [ Requisitos de administración](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| ¿Afectará el uso de Espacio de trabajo de Análisis a la recopilación de datos? | Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto del espacio de trabajo para ver qué hay disponible. Si arrastra accidentalmente un componente no válido al proyecto del espacio de trabajo o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. You can also start with a clean slate by clicking *[!UICONTROL Project]>[!UICONTROL New]*in the upper left menu. |
| ¿Cuántos grupos de informes se pueden ver en un proyecto de Analysis Workspace? | You can now create projects in Analysis Workspace with data from more [multiple report suites](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html). |
| ¿Cómo se implementa Analysis Workspace? | No se requiere implementación especial. Analysis Workspace está disponible en todas las empresas con Analytics estándar o premium. Sin embargo, son aplicables los permisos estándares para el contenido (como los grupos de informes y los componentes de proyecto) y para la depurar y compartir proyectos. Consulte [Administración y requisitos de acceso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| ¿Analysis Workspace cambia los informes preconfigurados en Adobe Analytics? | No. Como es un entorno separado, no se producen cambios en sus informes existentes o preconfigurados en Adobe Analytics. Puede seguir empleando los informes estándar tanto de Reports &amp; Analytics como del Report Builder mediante Analysis Workspace. |
| ¿Puedo usar Analysis Workspace para el Data Warehouse? | No se recomienda Analysis Workspace para exportación masiva de datos. Es un espacio de trabajo de visualización que crea proyectos de análisis con estilo de tablero. |
| ¿Cómo puedo optimizar el rendimiento de Analysis Workspace? | Consulte [Optimización del rendimiento](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). |
| ¿En qué se parecen y diferencian las capacidades de Analysis Workspace y los Ad Hoc Analysis? | Consulte [Analysis Workspace comparado con los Ad Hoc Analysis](/help/analyze/analysis-workspace/workspace-faq/adhocanalysis-vs-analysisworkspace.md). |

## Resolución de problemas

**Cuando arrastro una métrica, significa “Datos no válidos”.**

Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas una al lado de la otra.

**Cuando arrastro una métrica, no veo ningún dato real, solo ceros.**

Si ha creado correctamente un informe de área de trabajo pero no hay datos, puede comprobar algunas cosas:

* Doble verifique el grupo de informes y asegúrese de que esté lleno de datos.
* Si aplicó un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.
* Compruebe el intervalo de fechas en la esquina superior derecha y asegúrese de que está establecido en un valor que esperaba.
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.