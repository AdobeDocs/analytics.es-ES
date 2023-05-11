---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b5b6925b7425104335b592e98a556c2449fea5d9
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 52%

---

# Notas de la versión de Adobe Analytics actual (Mayo de 2023)

**Última actualización:** 11 de mayo de 2023

Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas en Adobe Analytics {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Relleno para entornos limitados que no sean de producción** | Al crear un flujo de datos del conector de origen de Analytics en un simulador para pruebas que no sean de producción, el relleno de los entornos limitados que no sean de producción estará limitado a 3 meses. Permanecerá a los 13 meses para los entornos limitados de producción. | N/A | 26 de abril de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye el uso compartido con personas ajenas a su organización o con personas pertenecientes a su organización que no estén aprovisionadas para Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link)<p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede desactivarla. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 de mayo de 2023 | Junio de 2023 |
| **Pantalla principal actualizada para la aplicación de paneles de Analytics (aplicación móvil)** | La nueva pantalla de inicio actualizada le permite ver todos los informes de valoración en una lista consolidada de informes de valoración.  Si tiene acceso a más de una organización en un inicio de sesión, todos los informes de valoración de sus organizaciones estarán disponibles en una sola lista. | N/A | 10 de mayo de 2023 |
| **Ordenar componentes en Analysis Workspace** | Ahora hay disponible una nueva opción de ordenación al ver componentes en el carril izquierdo o en el diccionario de datos de Analysis Workspace. Puede ordenar los componentes por Recomendado (los más utilizados), Alfabético o Categórico (tipo).<p>Anteriormente, solo se podían buscar o filtrar componentes. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | N/A | 10 de mayo de 2023 |
| **Eliminar filas que contienen dimensiones dinámicas de una tabla improvisada** | En una tabla improvisada de Analysis Workspace, ahora puede eliminar rápidamente filas específicas que contengan dimensiones dinámicas mediante el icono x . Al hacerlo, se aplica automáticamente una regla de filtro &quot;No es igual que&quot;.<p>Anteriormente, la única forma de eliminar filas que contenían dimensiones dinámicas era crear manualmente una regla en el cuadro de diálogo Filtro. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | N/A | 10 de mayo de 2023 |
| **Nuevo botón para añadir una visualización dentro de un panel** | Ahora hay disponible un nuevo botón en la parte inferior de cada panel en Analysis Workspace, lo que le permite añadir rápidamente una visualización. <p>Anteriormente, los únicos métodos para añadir una visualización a un panel eran arrastrar una visualización desde el carril izquierdo, duplicar o copiar una visualización existente o crear un panel en blanco. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#add-visualizations-to-a-panel)</p> | N/A | 17 de mayo de 2023 |
| **Vinculación profunda (aplicación móvil)** | Permite a los usuarios enviar vínculos a informes de valoración que los llevarán directamente al proyecto de informe de valoración de la aplicación. Esto facilita aún más el uso compartido de proyectos y aumenta la participación de una audiencia menos técnica. | Por determinar | Por determinar |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

AN-312098; AN-318309; AN-316675; AN-318173; AN-310359; AN-317613; AN-318836; AN-315744; AN-311772; AN-318719; AN-314074; AN-316651<!--"Verified" status-->; AN-318602; AN-315961; AN-317534; AN-318607; AN-316498; AN-316648; AN-318244; AN-317747; AN-318432; AN-318231; AN-317590; AN-318415; AN-318154; AN-316647; N-314417; AN-317614; AN-317725; AN-318114; AN-317876; AN-318052; AN-317966; AN-316477; AN-318036; AN-317931; AN-318045; AN-316246; AN-317281; AN-317879; AN-308077; AN-317708; AN-316115; AN-315963

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Migración a las credenciales de servidor a servidor de AdobeIO OAuth** | 11 de mayo de 2023 | Los clientes de API de Adobe Analytics y Livestream que utilicen credenciales de JWT de AdobeIO deben migrar a las credenciales de servidor a servidor de AdobeIO OAuth de **1 de enero de 2025**. Para obtener más información y cronologías, consulte el aviso de fin de vida útil en la tabla siguiente. |
| **Aviso: Nuevas direcciones IP utilizadas por las fuentes de datos y la salida de Data Warehouse de Adobe Analytics en el Centro de datos de Londres** | 27 de abril de 2023 | Para los clientes del Centro de datos de Londres que tengan solicitudes de fuentes de datos o informes de Data Warehouse que se envíen a un servicio FTP/SFTP, se deben añadir los siguientes intervalos de direcciones IP a la configuración del cortafuegos para permitir el acceso: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **Los procesos de búsqueda de dispositivos ahora utilizan un tercero para todas las búsquedas de dispositivos** | 3 de marzo de 2023 | El 2 de marzo de 2023, como parte del despliegue de asistencia para las recomendaciones del cliente, actualizamos nuestros procesos de búsqueda de dispositivos para todas las búsquedas de dispositivos. Anteriormente, solo habíamos utilizado terceros para búsquedas de dispositivos móviles. Como parte de ese despliegue, algunos sistemas operativos de escritorio se etiquetaron incorrectamente con el texto “mobile” (p. ej., “Mobile OS X 10.15.7” en lugar de “OS X 10.15.7”).<p>Durante el lanzamiento de Adobe en abril se coregirán estos nombres. El sistema de creación de informes de Analytics y CJA se actualizará de forma retroactiva, ya que su creación de informes busca el nombre del sistema operativo en función a un ID registrado como parte de los datos de evento. Una vez actualizado el valor de búsqueda correspondiente a un ID, se corregirá la creación de informes, incluidos los datos históricos. Para [!UICONTROL Fuentes de datos] clientes, los cambios son retroactivos si utiliza un proceso de búsqueda similar en el momento de generar el informe. Sin embargo, si almacena el valor del sistema operativo en los datos de evento, la creación de informes se actualizará en adelante únicamente. Consulte el [sistema operativo](/help/components/dimensions/operating-systems.md) para obtener más información. |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de AdobeIO OAuth** | 11 de mayo de 2023 | Los clientes de API de Adobe Analytics y Livestream que utilicen credenciales de JWT de AdobeIO deben migrar a las credenciales de servidor a servidor de AdobeIO OAuth de **1 de enero de 2025**. AdobeIO no permitirá la creación de nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor de OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor de OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración desde credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |
| **Final de la vida útil del servicio japonés de seguimiento Feature Phone** | 21 de marzo de 2023 | Solo para nuestros clientes japoneses: a **finales de mayo de 2023**, el servicio japonés de seguimiento Feature Phone (mod_ktrack) dejará de funcionar. Pedimos disculpas por las molestias, pero le pedimos que desinstale o deshabilite los módulos instalados en su servidor Apache. Consulte las páginas 27 y 28 de [este documento](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) como referencia. |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. En **Abril de 2023**, cualquier informe que estuviera programado para caducar después del 31 de diciembre de 2023 se actualizará automáticamente y se revertirá para que caduque el 31 de diciembre de 2023. Además, ya no puede programar informes futuros después del 31 de diciembre de 2023. |
| **EOL de la métrica [!UICONTROL Personas]** | 9 de marzo de 2023 | Con la retirada de [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=es), la métrica Personas relacionada con la cooperación entre dispositivos ya no es relevante. El 8 de mayo de 2023, se eliminará la métrica [!UICONTROL Personas]. En ese momento, redireccionaremos sus datos a la métrica [!UICONTROL Visitante único] para evitar que se estropeen los proyectos, los segmentos y las métricas calculadas.<p>**Nota**: La métrica [[!UICONTROL Personas] vinculada a análisis multidispositivo](/help/components/metrics/people.md) no se ve afectado por este anuncio. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 29 de septiembre de 2022 | Como parte del final de la vida útil de Reports &amp; Analytics, las [!UICONTROL Listas de publicación] están programadas para llegar al final de su vida útil en **diciembre de 2023**. No podrá crear [!UICONTROL Listas de publicación] nuevas ni acceder a las existentes para enviar o programar proyectos de [!UICONTROL Analysis Workspace]. |
| **Fin de la vida útil para Data Workbench** | 14 de septiembre de 2022 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**. Consulte [Anuncio del fin de la vida útil de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=es) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.23.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)
