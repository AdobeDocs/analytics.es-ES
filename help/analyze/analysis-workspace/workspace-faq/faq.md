---
description: Obtenga respuestas a preguntas comunes sobre Analysis Workspace.
title: Preguntas frecuentes
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 598
ht-degree: 83%

---

# Preguntas frecuentes

+++¿Cuáles son los requisitos previos para utilizar Analysis Workspace?
[Envío de datos a Adobe Analytics mediante la extensión de Adobe Analytics](/help/implement/launch/validate-publish-prod.md): El uso de Analysis Workspace requiere una implementación activa. Compruebe que su organización envía datos a Adobe antes de utilizar la herramienta. Otras implementaciones, como las implementaciones manuales heredadas, también pueden funcionar.
+++

+++¿Cuáles son los requisitos de administración y acceso de Analysis Workspace?
Consulte [Requisitos de administración](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++¿Afectará el uso de Analysis Workspace a la recopilación de datos?
Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto de Workspace para ver qué hay disponible. Si arrastra accidentalmente un componente no válido al proyecto de Workspace o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. También puede empezar con una pizarra limpia haciendo clic en **[!UICONTROL Proyecto]** > **[!UICONTROL Nuevo]** en el menú superior izquierdo.
+++

+++¿Cuántos grupos de informes se pueden ver en un proyecto de Analysis Workspace?
Ahora puede crear proyectos en Analysis Workspace con datos de [más de un grupo de informes](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md).
+++

+++¿Cómo se implementa Analysis Workspace?
No se requiere implementación especial. Analysis Workspace está disponible para todas las empresas con Analytics Standard o Premium. Sin embargo, son aplicables los permisos estándar para el contenido (como los grupos de informes y los componentes de proyecto) y para depurar y compartir proyectos. Consulte [Administración y requisitos de acceso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++¿Puedo usar Analysis Workspace para Data Warehouse?
No se recomienda Analysis Workspace para la exportación de datos en lote. Es un espacio de trabajo de visualización que crea proyectos de análisis similares a paneles.
+++

+++¿Cómo puedo optimizar el rendimiento de Analysis Workspace?

Consulte [Optimización del rendimiento](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++¿Cómo llegan los datos a su proyecto de Analysis Workspace?

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Datos en Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"} para ver un vídeo de demostración.

+++

+++¿Cómo puedo hacer un seguimiento del uso de Workspace?

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Seguimiento del registro](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"} para ver un vídeo de demostración.

+++

+++Al arrastrar una métrica, aparece el mensaje “Datos no válidos”. ¿Cómo resuelvo este problema?

Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas una al lado de la otra.

+++

+++Cuando arrastro una métrica, no veo ningún dato real, solo ceros. ¿Cómo puedo solucionar este problema?

Si ha creado correctamente un informe de espacio de trabajo pero no hay datos, puede comprobar algunas cosas:

* Compruebe el grupo de informes y asegúrese de que se rellena con datos.
* Si aplicó un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.
* Compruebe el intervalo de fechas en la esquina superior derecha y compruebe que está establecido en un valor que esperaba.
* Vaya al sitio web y utilice [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es) para validar que se están recopilando datos.


+++

+++Como usuario de solo lectura, ¿qué acciones puedo realizar en Analysis Workspace?
Cuando un proyecto se comparte como de solo lectura, todas las funciones y características de edición se desactivan por completo y los destinatarios solo pueden cambiar el menú desplegable para aplicar un filtro al panel de forma predefinida.
+++
