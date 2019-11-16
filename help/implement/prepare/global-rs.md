---
title: Grupos de informes globales en Adobe Analytics
description: Comprender las ventajas y los requisitos para utilizar un grupo de informes globales.
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# Consideraciones sobre el grupo de informes globales

Un grupo de informes globales es un grupo de informes que recopila datos de todos los dominios y aplicaciones que posee su organización. Esta técnica de recopilación de datos requiere preparación y puede requerir la coordinación entre equipos dentro de la organización.

## Ventajas

Adobe recomienda implementar un grupo de informes globales en la mayoría de los casos.

* **** Datos agregados: Los grupos de informes globales le permiten ver los KPI y los eventos de éxito en los sitios que posee. Los grupos de informes virtuales y de segmentación se pueden utilizar para ver datos específicos del sitio.
* **** Compatibilidad con Analytics entre dispositivos: CDA requiere un grupo de informes que recopila datos de varios lugares, como su sitio web y su aplicación móvil. Los dispositivos independientes pueden unir los datos si se implementan correctamente. Consulte Análisis [entre dispositivos](../../components/cda/cda-home.md) en la guía del usuario Componentes para obtener más información.
* **** No se necesita más de un grupo de informes: Todos los datos se pueden recopilar en un solo grupo de informes, por lo que es menos probable que un programador envíe datos erróneamente al grupo de informes incorrecto.
* **** No es necesario realizar resúmenes: Los resúmenes son una característica bastante antigua que agrega datos de grupos de informes individuales diariamente. Los resúmenes no anulan la duplicación de datos de visitas o visitantes, lo que puede provocar un aumento de los números. Consulte [Resúmenes](../../admin/c-manage-report-suites/rollup-report-suite.md) en la guía del usuario de administración para obtener más información.

> [!NOTE] Coordinar la implementación de un grupo de informes globales es un proyecto grande. Adobe recomienda trabajar con un consultor para reducir las complicaciones y los problemas que surgen.

## Inicio de una nueva implementación con un grupo de informes global

Utilice las siguientes directrices generales para comprender el proceso de implementación de un grupo de informes globales.

1. Cree el grupo de informes globales en Adobe Analytics. Consulte [Creación de un grupo](../../admin/admin-console/create-report-suite.md) de informes en la guía del usuario Administrador para obtener más información.
2. Trabaje con los equipos de su organización responsables de cada dominio. Muchos equipos tienen requerimientos de informes específicos de su área de negocio.
3. Registre y agregue todos estos requisitos en un documento [de diseño de](solution-design.md)solución. Si los equipos tienen requisitos similares para una dimensión, pueden utilizar la misma variable personalizada. Por ejemplo: si el sitio A y el sitio B requieren una dimensión de ruta de exploración, las implementaciones para ambos sitios pueden enviar esos datos a través de eVar1.
   > [!IMPORTANT] Asegúrese de que cualquier variable personalizada dada se utilice de manera similar en los distintos dominios. No utilice la misma eVar o evento para distintos fines en los distintos sitios.
4. Asegúrese de que cada dominio tenga una capa de datos para simplificar la recopilación de datos. Los datos se pueden recopilar sin una capa de datos, pero la fiabilidad y la longevidad de la implementación disminuyen, especialmente a medida que el sitio pasa por rediseños.
5. Utilice Adobe Experience Platform Launch para implementar Analytics. Es probable que distintos sitios requieran diferentes elementos de datos. Utilice reglas específicas de cada dominio para asegurarse de que cada elemento de datos se rellena correctamente y, a continuación, asigne esos elementos de datos a sus eVars y eventos respectivos. Consulte Información general sobre [el lanzamiento](https://docs.adobe.com/content/help/en/launch/using/overview.html) en la guía del usuario de Adobe Experience Platform Launch.

## Modificación de una implementación existente con un grupo de informes global

El proceso de mover una implementación existente en varios sitios a un único grupo de informes globales requiere más tiempo y coordinación entre los equipos de su organización.

1. Determine si desea utilizar uno de los grupos de informes existentes o empezar a utilizarlo de nuevo con un nuevo grupo de informes. Si desea cambiar los usos de las variables existentes en la implementación, se recomienda comenzar con un nuevo grupo de informes.
2. Determinar una fecha de corte para el momento en que desee realizar el cambio a un grupo de informes globales. El mejor momento para realizar un recorte es entre dos períodos de informes significativos, como un trimestre fiscal o un año.
3. Siga los pasos anteriores (cree un grupo de informes, recopile los requisitos de informes en un documento de diseño de solución y establezca una capa de datos en cada sitio). Al implementar Launch, valide la implementación con una versión de desarrollo del sitio web.
4. Una vez que haya confirmado que la implementación está funcionando en dev, envíe la implementación de Launch a la fecha de cambio.

## Páginas relacionadas

[Cambio del etiquetado de grupos múltiples a un grupo de informes globales y grupos](../../components/vrs/vrs-considerations.md)de informes virtuales[Comparación de resúmenes y grupos de informes globales](../../admin/c-manage-report-suites/rollup-report-suite.md)