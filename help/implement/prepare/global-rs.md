---
title: Grupos de informes globales en Adobe Analytics
description: Comprender las ventajas y los requisitos para utilizar un grupo de informes globales
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 96%

---

# Consideraciones sobre el grupo de informes globales

Un grupo de informes globales es un grupo de informes que recopila datos de todos los dominios y las aplicaciones que posee su organización. Esta técnica de recopilación de datos necesita preparación y puede requerir una coordinación entre equipos dentro de la organización.

## Ventajas

Adobe recomienda implementar un grupo de informes globales en la mayoría de los casos.

* **Datos agregados:** los grupos de informes globales le permiten ver los KPI y los eventos de éxito en los sitios que posee. Los grupos de informes virtuales y de segmentación se pueden utilizar para ver datos específicos del sitio.
* **Compatibilidad con Cross-Device Analytics:** CDA necesita un grupo de informes que recopile datos de varios lugares, como su sitio web y su aplicación móvil. Los dispositivos independientes pueden unir los datos si se implementan correctamente. Consulte [Cross-Device Analytics](../../components/cda/overview.md) en la guía del usuario de componentes para obtener más información.
* **No se necesita más de un grupo de informes:** todos los datos se pueden recopilar en un solo grupo de informes, por lo que es menos probable que un programador envíe datos por error al grupo de informes equivocado.
* **No es necesario realizar resúmenes:** los resúmenes son una característica bastante antigua que agrega datos de grupos de informes individuales diariamente. Los resúmenes no anulan la duplicación de datos de visitas o visitantes, lo que puede provocar un aumento de las cifras. Consulte [Resúmenes](../../admin/tools/manage-rs/rollup-report-suite.md) en la guía del usuario de administración para obtener más información.
* **Ahorre tiempo:** los proyectos, las clasificaciones, los segmentos y las métricas calculadas de Workspace están vinculados al mismo grupo de informes globales. Los administradores invierten menos tiempo en administrar estos componentes y la gobernanza de datos.
* **Atribución más precisa entre marcas:** si una visita comienza en un sitio y luego hace clic en otro antes de activar un evento de éxito, la atribución se recopila con precisión. Por ejemplo: un visitante hace clic en un vínculo de búsqueda pagada y accede al sitio A. Luego hace clic en un vínculo al sitio B, para después realizar una compra. Un grupo de informes globales atribuye correctamente la compra a la búsqueda pagada.
* **Implementación simplificada:** dado que todas las marcas y sitios envían datos al mismo grupo de informes, las implementaciones de cada sitio se alinean. Este control obligatorio garantiza que una dimensión o métrica específica se guarde en la misma eVar o en el mismo evento. Esta simplificación beneficia a administradores, probadores, propietarios de administración de etiquetas y analistas.

>[!NOTE]
>
>Coordinar la implementación de un grupo de informes globales no es tarea fácil. Adobe recomienda trabajar con un consultor para reducir las complicaciones y los problemas que puedan surgir.

## Inicio de una nueva implementación con un grupo de informes global

Utilice las siguientes directrices generales para comprender el proceso de implementación de un grupo de informes globales.

1. Cree el grupo de informes globales en Adobe Analytics. Consulte [Creación de un grupo de informes](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md) en la guía del usuario de administración para obtener más información.
1. Trabaje con los equipos de su organización responsables de cada dominio. Muchos equipos incluyen requisitos de informes específicos de su área de negocio.
1. Registre y agregue todos estos requisitos en un [documento de diseño de solución](solution-design.md). Si los equipos tienen requisitos similares para una dimensión, pueden utilizar la misma variable personalizada. Por ejemplo: si el sitio A y el sitio B exigen una dimensión de ruta de exploración, las implementaciones para ambos sitios pueden enviar esos datos a través de eVar1.

   >[!IMPORTANT]
   >
   >Asegúrese de que cualquier variable personalizada dada se utilice de manera similar en los distintos dominios. No utilice la misma eVar o evento para distintos fines en cada sitio.
1. Asegúrese de que cada dominio tenga una capa de datos para simplificar la recopilación de datos. Los datos se pueden recopilar sin una capa de datos, pero la fiabilidad y la longevidad de la implementación disminuyen, especialmente a medida que el sitio se rediseña con el tiempo.
1. Uso de etiquetas en Adobe Experience Platform para implementar Analytics. Es probable que distintos sitios requieran diferentes elementos de datos. Utilice reglas específicas de cada dominio para asegurarse de que cada elemento de datos se rellena correctamente y, a continuación, asigne esos elementos de datos a sus eVars y eventos respectivos. Consulte [información general sobre las etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es).
1. Incluya el [servicio de Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es) y use la función [`appendVisitorIDsTo`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html?lang=es). Esta función combina datos de visitantes cuando los usuarios hacen clic de un dominio a otro.

## Modificación de una implementación existente con un grupo de informes global

El proceso de mover una implementación existente en varios sitios a un único grupo de informes globales requiere más tiempo y coordinación entre los equipos de su organización.

1. Determine si desea utilizar uno de los grupos de informes existentes o empezar a utilizarlo de nuevo con un nuevo grupo de informes. Si desea cambiar los usos de las variables existentes en la implementación, se recomienda comenzar con un nuevo grupo de informes.
2. Determine una fecha límite para el momento en que desee realizar el cambio a un grupo de informes globales. El mejor momento para realizar una migración es entre dos períodos de informes significativos o junto con los cambios más importantes en el sitio. Algunos ejemplos son el inicio de un trimestre o año fiscal, durante una actualización del sitio o el cambio a un nuevo sistema de administración de etiquetas.
3. Siga los pasos anteriores (cree un grupo de informes, recopile los requisitos de informes en un documento de diseño de solución y establezca una capa de datos en cada sitio). Al implementar etiquetas en Adobe Experience Platform, valide la implementación con una versión de desarrollo del sitio web.
4. Una vez que haya confirmado que la implementación funciona en el desarrollo, publique la implementación de etiquetas en la fecha de migración.

>[!MORELIKETHIS]
>
>[Cambio del etiquetado de grupos múltiples a un grupo de informes globales y grupos de informes virtuales](../../components/vrs/vrs-considerations.md)
>>[Comparando resúmenes y grupos de informes globales](../../admin/tools/manage-rs/rollup-report-suite.md)
