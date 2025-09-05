---
description: Obtenga respuestas a preguntas comunes sobre Analysis Workspace.
title: 'Preguntas frecuentes '
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 93%

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
No se requiere implementación especial. Analysis Workspace está disponible en todas las empresas con Analytics estándar o premium. Sin embargo, son aplicables los permisos estándares para el contenido (como los grupos de informes y los componentes de proyecto) y para la depurar y compartir proyectos. Consulte [Administración y requisitos de acceso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++¿Puedo usar Analysis Workspace para el Data Warehouse?
No se recomienda Analysis Workspace para exportación masiva de datos. Es un espacio de trabajo de visualización que crea proyectos de análisis con estilo de tablero.
+++

+++¿Cómo puedo optimizar el rendimiento de Analysis Workspace?

Consulte [Optimización del rendimiento](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++¿Cómo llegan los datos a su proyecto de Analysis Workspace?

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Datos en Analysis Workspace](https://video.tv.adobe.com/v/31072?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

+++

+++¿Cómo puedo hacer un seguimiento del uso de Workspace?

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Seguimiento del registro](https://video.tv.adobe.com/v/29768?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

+++

+++Cuando arrastro una métrica, significa &quot;Datos no válidos&quot;. ¿Cómo resuelvo este problema?

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
