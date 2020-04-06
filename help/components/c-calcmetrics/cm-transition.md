---
description: Estos cambios en la forma en que funcionan las métricas calculadas en Analytics pueden afectarle.
title: Preguntas frecuentes
uuid: 9b7f1cd1-b969-4b15-8af1-969d816b65b8
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Preguntas frecuentes

Es posible que estos cambios en la forma en la que las métricas calculadas funcionan en [!DNL Analytics] le sorprendan.

[¿Cómo puedo acceder al Creador de métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[¿Cómo puedo acceder al Administrador de métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[¿Por qué veo tantas métricas calculadas con el mismo nombre?](/help/components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[¿Qué ha sucedido con mis Métricas calculadas globales?](/help/components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[¿Qué les ha sucedido a las Métricas calculadas globales que se compartieron entre Empresas de inicio de sesión?](/help/components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[¿Qué les ha sucedido a las Métricas calculadas con una clasificación de Numérico o Numérico2?](/help/components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[¿Qué les ha sucedido a las Métricas permanentes?](/help/components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[¿Qué pasa si necesito conocer Métricas calculadas en base a métricas de visitante únicas diarias/semanales/mensuales/trimestrales/anuales?](/help/components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[¿Qué sucede con las Métricas calculadas creadas o administradas con los antiguos métodos de API del grupo de informes?](/help/components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[¿Los datos actuales admiten todo tipo de Métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[¿Qué significa &quot;No se ha introducido un nombre&quot; conjuntamente con las métricas calculadas migradas?](/help/components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[¿Qué les sucede a las métricas calculadas de un usuario si se elimina dicho usuario?](/help/components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[¿Por qué veo métricas calculadas “Desconocidas” que no son válidas para otros grupos de informes a pesar de que pueden crearse y aplicarse en ellos?](/help/components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[¿Por qué no se han guardado los cambios que he realizado en mis métricas calculadas antiguas?](/help/components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[¿Por qué no aparecen mis métricas calculadas en el informe de Canales de marketing?](/help/components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[¿Por qué algunas métricas calculadas muestran fórmulas sin el paréntesis añadido?](/help/components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[(Solo Ad Hoc Analysis) ¿Las métricas calculadas con definiciones de segmento en línea o incrustadas siguen siendo compatibles?](/help/components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[(Solo en el Report Builder) ¿Por qué han desaparecido las métricas calculadas de mis solicitudes?](/help/components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[¿Cómo funcionan los Totales de métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## ¿Cómo puedo acceder al Creador de métricas calculadas? {#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Click **[!UICONTROL + Add]** at the top of the Calculated Metric Manager, or
* In any Analytics report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Add]**.

## ¿Cómo puedo acceder al Administrador de métricas calculadas? {#section_DD0BD13E9EC940268EBE8BC88241A152}

* Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** en el panel de navegación izquierdo. A continuación, haga clic en **[!UICONTROL Calculated Metrics]**.

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## ¿Por qué veo tantas métricas calculadas con el mismo nombre? {#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(Anteriormente, las métricas calculadas globales no eran propiedad de ningún usuario administrador específico y eran visibles para todos los usuarios de ese grupo de informes. Las métricas se segregaron por grupo de informes. Si una métrica en un grupo de informes tuviera el mismo nombre que una métrica en un grupo de informes diferente, simplemente los usuarios la verán como la misma métrica cuando cambien los grupos de informes).

Ahora, las métricas ya no están segregadas por grupos de informes. Si una métrica de un grupo de informes tenía el mismo nombre que una métrica en un grupo de informes diferente, ambas estarán visibles en el Creador de métricas calculadas y en el Selector de métricas y podrían aparecer como métricas de duplicado aunque tengan o no la misma definición.

Solo podía ver un número de métricas calculadas con el mismo nombre (pero creadas en distintos grupos de informes) si desmarcaba la casilla de verificación (Solo `<report suite>`) como se muestra aquí:

![](assets/report_suite.png)

**Qué debe hacer**

Considere la posibilidad de consolidar métricas calculadas con nombres y definiciones similares, pero tenga cuidado al hacerlo. Puede comprobar el grupo de informes de una métrica calculada en el Administrador de métricas calculadas para verificar su grupo de informes original. También debe comprobar las definiciones de las métricas al eliminar duplicados potenciales para asegurarse de que está consolidando correctamente las métricas.

>[!NOTE] A pesar de que las métricas calculadas ya no están ligadas a un grupo de informes específico y pueden utilizarse en cualquier grupo de informes que sea visible para la empresa de inicio de sesión, el grupo de informes en el que se ha creado o guardado por última vez la métrica calculada aún será visible en el Administrador de métricas calculadas.

>[!NOTE] Aunque elimine una métrica calculada, cualquier informe de panel o marcador que haga referencia a esa métrica seguirá funcionando.

## ¿Qué ha sucedido con mis Métricas calculadas globales? {#section_7351D4C7361F4ABAA1B43F8E89AAD211}

(Anteriormente, un administrador podía crear métricas calculadas (conocidas como &quot;métricas calculadas globales&quot; o &quot;métricas calculadas del grupo de informes&quot;) en un grupo de informes a través de las Herramientas de administración.

Las métricas calculadas globales ahora son propiedad del primer usuario administrador en la lista de usuarios administradores de la compañía de inicio de sesión. De forma predeterminada, se compartirán con &quot;Todos&quot;. Este patrón sigue el mismo modelo de uso compartido y los mismos planes de migración que los segmentos.

**Qué debe hacer**

Nada. Sin embargo, el nuevo propietario del administrador debe actuar con precaución al modificar o eliminar estas métricas calculadas, ya que pueden utilizarse en una serie de informes y paneles con marcador.

>[!NOTE] Aunque elimine una métrica calculada, cualquier informe de panel o marcador que haga referencia a esa métrica seguirá funcionando.

## ¿Qué les ha sucedido a las Métricas calculadas globales que se compartieron entre Empresas de inicio de sesión? {#section_59E5CD948ED643AE9AD3D2E4277647F8}

(Anteriormente, un administrador podía crear métricas calculadas (conocidas como &quot;métricas calculadas globales&quot; o &quot;métricas calculadas del grupo de informes&quot;) en un grupo de informes a través de las Herramientas de administración. Estas métricas se pueden &quot;compartir&quot; a través de compañías de inicio de sesión agregando el grupo de informes a varias compañías de inicio de sesión).

Las métricas calculadas globales ya no se pueden compartir entre las compañías de inicio de sesión. Ya no están enlazados a un grupo de informes específico, sino que están ligados a una compañía de inicio de sesión específica. Métricas calculadas que se compartieron entre compañías de inicio de sesión

* Todas las empresas de inicio de sesión con acceso a ese grupo de informes se han migrado.
* De forma predeterminada, estarán configuradas como “compartido con todos”.
* Serán copias independientes de todas las demás empresas de inicio de sesión.

>[!NOTE] Si la métrica calculada se ha utilizado en un marcador, tablero, alerta o informe programado, la edición de la nueva copia NO afectará la antigua métrica calculada conservada.

## ¿Qué les ha sucedido a las Métricas calculadas con una clasificación de Numérico o Numérico2? {#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs. Sin embargo, no serán compatibles con ningún informe al que se haya aplicado un segmento.

Además, las métricas calculadas con una clasificación Numérica o Numérica2 no serán compatibles con los siguientes componentes: [!UICONTROL Ad Hoc Analysis], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] informes [!UICONTROL Anomaly Detection], y [!UICONTROL Contribution Analysis]. Al crear o editar una métrica calculada con una clasificación Numérica o Numérica2, verá una advertencia de compatibilidad en la que se indica que la métrica calculada no es compatible con determinadas áreas del producto.

**Qué debe hacer**

Evite crear métricas calculadas con clasificaciones numéricas1 o numéricas2 si la métrica está pensada para utilizarse con un segmento o con cualquiera de los componentes no compatibles.

## ¿Qué les ha sucedido a las Métricas permanentes? {#section_AEDB02EF24584DAD8731BED9DDCE4F48}

Las métricas permanentes (o métricas de todo el tiempo) ya no son compatibles y no son visibles en la interfaz de usuario de [!UICONTROL Reports & Analytics] o en cualquier otra interfaz de usuario. La API de informes no puede consultarlas.

Cualquier marcador, panel, informe programado o alerta que contenga una métrica de todo el tiempo seguirá ejecutándose sin esa métrica siempre y cuando al menos otra métrica válida esté también en el informe. Si la única métrica en el marcador, panel, informe programado o alerta es una métrica de todo el tiempo, el informe ya no se ejecutará.

## ¿Qué pasa si necesito conocer Métricas calculadas en base a métricas de visitante únicas diarias/semanales/mensuales/trimestrales/anuales? {#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and Reporting API.

Sin embargo, estas métricas no se admitirán en los siguientes componentes: [!UICONTROL Segments], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] informes [!UICONTROL Anomaly Detection], y [!UICONTROL Contribution Analysis]. Cuando crea u edita una métrica calculada basada en métricas de Visitantes únicos, verá una advertencia de compatibilidad acerca de que la métrica no es compatible con ciertas áreas del producto.

Utilice una métrica de Visitante único base en un informe con un segmento. Puede crear una Métrica calculada basada en una métrica de Visitante único, sin embargo, esa métrica calculada no puede aplicarse en un informe con un segmento ni puede tener un segmento incrustado.

## ¿Qué sucede con las Métricas calculadas creadas o administradas con los antiguos métodos de API del grupo de informes? {#section_13ED1BAD02634674BDAEB479B060A4B6}

Anteriormente, guardar una métrica calculada con el método API (1.3 o 1.4) ReportSuite.SaveCalculatedMetrics era lo mismo que crear o actualizar una métrica calculada en la Consola de administración. Lo mismo se aplica a ReportSuite.DeleteCalculatedMetrics. Además, la lista de las métricas calculadas que se mostraban en la Consola de administración o al llamar a ReportSuite.GetCalculatedMetrics era la misma.

Ahora, los métodos API ReportSuite CalculatedMetrics (1.3 o 1.4) seguirán guardando, eliminando o recuperando las métricas calculadas usando el antiguo almacén. Las métricas calculadas existentes se migrarán y serán visibles en el nuevo Creador de métricas calculadas. **Las nuevas métricas calculadas creadas con los métodos API solo serán visibles en la API. Seguirán utilizándose en la API de Sistema de informes.**

**Qué debe hacer**

Si necesita utilizar tanto la API como el Creador de métricas calculadas, debe dejar de utilizar los métodos de API ReportSuite CalculatedMetrics y, en su lugar, utilizar los nuevos métodos de API CalculatedMetrics (Get, Save, Delete y GetFunctions).

## ¿Los datos actuales admiten todo tipo de Métricas calculadas? {#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

Los datos actuales no admiten métricas calculadas que contengan segmentos o funciones estadísticas. Las únicas funciones admitidas son las funciones matemáticas básicas como adición, eliminación, multiplicación, división y negación (-x).

## ¿Qué significa &quot;No se ha introducido un nombre&quot; conjuntamente con las métricas calculadas migradas? {#section_C90CBB72A67644F38D583301981F8D03}

&quot;No se ha introducido un nombre&quot; significa que no hay ningún nombre de métrica asociado con esta métrica migrada (simplemente una fórmula sin un nombre descriptivo).

## ¿Qué les sucede a las métricas calculadas de un usuario si se elimina dicho usuario? {#section_42ED4C15830540879C4A161423690E5A}

Todas las métricas calculadas que haya creado este usuario también se eliminarán. Sin embargo, las métricas calculadas eliminadas seguirán funcionando como parte de los marcadores, paneles o informes programados guardados.

## ¿Por qué veo métricas calculadas “Desconocidas” que no son válidas para otros grupos de informes a pesar de que pueden crearse y aplicarse en ellos? {#section_6772818EFDED46E9B7095D64C3B77211}

La interfaz de usuario muestra “desconocida” si la métrica calculada contiene métricas o dimensiones base que no existen para el grupo de informes seleccionado.

## ¿Por qué no se han guardado los cambios que he realizado en mis métricas calculadas antiguas? {#section_81CDEFCA1FD542579AF183DA1494EAF0}

Esto puede deberse al tiempo que se produce la migración a la nueva base de datos de métricas calculadas, que tuvo lugar entre el 15 de junio y el 18 de junio de 2015.

**Qué debe hacer**

Tendrá que rehacer los cambios realizados en las métricas heredadas.

## ¿Por qué no aparecen mis métricas calculadas en el informe de Canales de marketing? {#section_FC350359A775433AB5F43C7CAB304D62}

(Anteriormente, todas las métricas calculadas se enumeraban en el selector de métricas de los informes de Canales de marketing con una opción de primer toque y último toque).

Ahora, en el selector de métricas de los informes de Canales de marketing solo estarán disponibles las métricas calculadas que tengan su tipo de asignación establecido específicamente en Primer toque o Último toque en el creador de métricas calculadas. Tenga en cuenta que las métricas calculadas que ya se hayan aplicado a los informes de Canal de marketing seguirán aplicándose y funcionando como antes. Para crear una métrica calculada para Canales de marketing, haga clic en el icono de configuración del creador de métricas y seleccione Primer toque o Último toque como tipo de asignación. Recuerde que si lo hace, la métrica calculada será compatible únicamente con los informes de Canal de marketing y no se podrán utilizar en ningún otro informe.

## ¿Por qué algunas métricas calculadas muestran fórmulas sin el paréntesis añadido? {#section_AC0D1E9714AD487F9A1C73359F518B5E}

Durante la migración, Adobe eliminó los paréntesis superfluos de algunas fórmulas. Solo se eliminaron los paréntesis que no afectan a la forma en que se calcula la métrica. Esto no cambiará los datos, tan solo simplifica la fórmula.

## (Solo Ad Hoc Analysis) ¿Las métricas calculadas con definiciones de segmento en línea o incrustadas siguen siendo compatibles? {#section_B25C924A282F49388AB604E3D826F44C}

Las métricas calculadas creadas en análisis ad hoc anteriormente podían contener definiciones de segmentos en línea. Esto ya no es posible.

**Qué debe hacer**

Debe guardar el segmento expresamente. Las métricas existentes calculadas con definiciones de segmento en línea seguirán ejecutándose correctamente y podrán verse desde Ad Hoc Analysis, pero no podrán guardarse sin guardar explícitamente el segmento.

## (Solo en el Report Builder) ¿Por qué han desaparecido las métricas calculadas de mis solicitudes? {#section_DA4792FE5D7945218CD5E6328DE08E82}

Si la solicitud se ha creado en la versión 5.2 y contiene métricas calculadas, estas métricas no serán visibles en la versión 5.1 (o en versiones anteriores). Esto se debe a que las métricas calculadas ahora utilizan ID globales (ID no específicos de grupos de informes).

**Qué debe hacer**

Debe actualizar a la versión 5.2 para poder ver estas métricas.

## ¿Cómo funcionan los Totales de métricas calculadas? {#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports & Analytics] shows a calculated metrics total in [!UICONTROL Reports & Analytics], it&#39;s just applying the formula to the total. Por ejemplo: el total de la métrica calculada Pedidos/Visita toma el total de pedidos y los divide por el total de visitas. Sin embargo, en algunos casos, el total de la métrica calculada no es sólo la suma de los elementos de línea, sino un total para el sitio.

Ejemplo 1: Visitantes para un término de búsqueda: es posible que el mismo visitante haya buscado varios términos, por lo que en este caso, el total de visitantes no es igual a la suma de los elementos de línea.

Ejemplo 2: vistas de página en productos: en el carro de compras, puede haber varios productos, por lo tanto, hay varias vistas de página para el carro de compras. Para obtener más información sobre cómo comparar la suma de elementos de línea con los totales del informe, consulte [este artículo](https://helpx.adobe.com/es/analytics/kb/sum-line-items-different-from-total.html)de la base de conocimiento.
