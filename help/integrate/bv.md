---
title: Integración de visibilidad de la marca
description: Integrar la Visibilidad de la marca con Adobe Analytics
feature:
role: User
source-git-commit: 841b09d487fb965fb2a5fce4a39a7480a5b01012
workflow-type: tm+mt
source-wordcount: '2637'
ht-degree: 1%
---

# Integración de Adobe Brand Visibility

[Adobe Brand Visibility](https://experienceleague.adobe.com/es/docs/llm-optimizer/using/home) es una aplicación generativa con prioridad de IA para la optimización de motores generativos, diseñada para ayudar a las marcas a mejorar su visibilidad, precisión e influencia en entornos de búsqueda impulsados por IA. Brand Visibility proporciona perspectivas sobre la presencia de marca en respuestas generadas por IA, ofrece recomendaciones de contenido prescriptivo y automatiza las correcciones de optimización.

La IA se ha convertido en un canal de descubrimiento principal. Los agentes del modelo de lenguaje grande (LLM), como ChatGPT, Claude, Copilot y Perplexity, rastrean el contenido de la marca.

>[!NOTE]
>
>Anteriormente, la visibilidad de la marca se conocía como **LLM Optimizer (LLMO)**. Algunos documentos de Adobe pueden seguir utilizando la terminología anterior de LMO durante la transición.


>[!PREREQUISITES]
>
>Debe tener una oferta de pago por Visibilidad de la marca aprovisionada y conectada a la configuración de Experience Platform a través del conector administrado.


>[!IMPORTANT]
>
>Como parte de esta integración, algunos procesos temporales de datos de Visibilidad de la marca tienen lugar en Estados Unidos. En última instancia, los datos se almacenan en la región designada, según la configuración del contrato de Adobe Analytics.

Si utiliza Customer Recorrido Analytics, una integración entrante independiente y más rica obtiene los mismos datos de tráfico de CDN subyacentes en Customer Journey Analytics a través de Adobe Experience Platform. Esa integración ya está disponible. Ver [integración de Visibilidad de la marca con Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/integrations/bv). Si tiene Customer Journey Analytics, revise primero esa integración, ya que expone más campos y admite la unión de datos de Visibilidad de la marca con otros conjuntos de datos. La integración de Analytics que se describe en esta guía está diseñada para clientes que utilizan Adobe Analytics sin tener acceso a Customer Journey Analytics ni obtener una licencia para él.


## Casos de uso

Puede beneficiarse de la integración entre Adobe Analytics y Brand Visibility de dos maneras:

* **Integración entrante**: utilice los datos de Visibilidad de la marca en Adobe Analytics para medir el tráfico impulsado por LLM (rastreadores de bots, solicitudes RAG, actividad del agente) junto con los datos web y móviles existentes. Por ejemplo, puede realizar lo siguiente:

  * Mida el tráfico impulsado por LLM por fuente de agente junto con los canales tradicionales.

  * Identificar el contenido que consume mucho los LLM pero que no tiene el rendimiento suficiente en la conversión humana.

  * Detectar dónde fallan las solicitudes del agente LLM en las rutas críticas.

  * Comparar la demanda de bots LLM de una página con las conversiones e ingresos de esa página en los datos web, coincidiendo en los niveles de URL y host.

* **Integración saliente**: envíe datos de rendimiento de Adobe Analytics a Brand Visibility para que pueda optimizar la visibilidad de IA para las fuentes de LLM que le envían tráfico valioso, como ChatGPT o Perplexity. Por ejemplo, puede realizar lo siguiente:

  * Vea qué fuentes de LLM envían visitantes humanos que siguen convirtiendo o generando ingresos. Adobe Analytics mide esto a partir del tráfico web al que se hace referencia, no del conjunto de datos de bots.
  * Clasifique las fuentes de LLM según el valor descendente de los visitantes humanos que envían y, a continuación, centre su trabajo de visibilidad de la IA en las fuentes que funcionan mejor.


## Integración entrante

En esta sección se describen los requisitos previos y los pasos de configuración para la integración entrante de **Adobe Brand Visibility → Adobe Analytics**.


El conector de Adobe Analytics entrante se configura por grupo de informes a través del **Administrador de grupos de informes**, como se describe en la sección 6.

>[!PREREQUISITES]
>
>Adobe Brand Visibility debe reenviar y recibir los registros de acceso de CDN para cada sitio de Visibilidad de la marca antes de poder habilitar el conector de Brand Visibility → Adobe Analytics.
>
>Este requisito se aplica en **cada sitio de Visibilidad de la marca**. No se debe suponer que una configuración de CDN o una fuente de registro para un sitio, dominio o subdominio cubre otro sitio a menos que Adobe confirme esa cobertura.
>
>
>Antes de activar el conector, confirme lo siguiente:
>
>1. La CDN o la canalización de registros relevantes están configuradas para reenviar los registros de acceso necesarios al destino proporcionado por Adobe.
>1. La visibilidad de la marca ha confirmado que se están recibiendo y detectando registros para el sitio correspondiente.
>1. Los datos están visibles en el tablero de tráfico de la Visibilidad de la marca de ese sitio.
>
>El reenvío de registros de BYOCDN proporciona los datos de solicitud de CDN del lado del servidor que se utilizan para el análisis del tráfico real. Los datos no dependen de las etiquetas de JavaScript que se ejecuten en un explorador. Sin la fuente de registro de CDN necesaria, el conector no tendrá datos de tráfico que introducir en el grupo de informes.
>
>Consulte [Referencia de reenvío de registros BYOCDN](https://experienceleague.adobe.com/es/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) para obtener más información.


>[!IMPORTANT]
>
>Como parte de esta integración, algunos procesos temporales de datos de Visibilidad de la marca tienen lugar en Estados Unidos. En última instancia, los datos se almacenan en la región designada, según la configuración del contrato de Adobe Analytics.


### Funcionamiento

La Visibilidad de la marca entrante → la integración de Adobe Analytics agrega un conjunto de **variables reservadas** al grupo de informes. Estas variables llevan datos de resumen sobre el tráfico de bots y agentes automatizados detectado en su sitio web, incluido el tráfico basado en LLM, originado en los mismos registros de acceso de CDN descritos en los [requisitos previos](#inbound-integration).

Este tráfico generalmente no ejecuta las etiquetas JavaScript del explorador y no se captura a través de la implementación de Adobe Analytics existente. Las variables reservadas le permiten ver el tráfico dentro del mismo grupo de informes que ya utiliza para el sitio.

Las siguientes variables reservadas se agregan cuando el conector está habilitado:

| Notificado como | Tipo | Notas |
|---|---|---|
| URL | Dimensión | La URL de la página asociada con la solicitud. |
| Tipo de bot | Dimensión | El tipo de bot o agente automatizado que realizó la solicitud (por ejemplo, un rastreador de IA con nombre). |
| Agente de usuario | Dimensión | Cadena del agente de usuario registrada por el bot o el agente. |
| Estado | Dimensión | El código de estado HTTP devuelto para la solicitud. |
| Referer | Dimensión | El valor del referente HTTP de la solicitud, cuando está presente. |
| Solicitudes | Métrica | Recuento de solicitudes de CDN de bots y agénticas. |


#### Cobertura comparada con Customer Journey Analytics

La integración entrante de CJA se basa en un conjunto de datos de resumen de solicitudes de CDN más amplio y admite campos adicionales (por ejemplo, host y proveedor de CDN) además de unirse a otros conjuntos de datos en Customer Journey Analytics. La integración de Adobe Analytics es un conjunto más pequeño, nativo del grupo de informes, de variables reservadas y diseñadas para funcionar dentro del modelo de datos existente de Analytics. Si sus necesidades de creación de informes van más allá de los campos enumerados arriba, evalúe la integración de CJA.

#### Limitaciones importantes

&#x200B;- No se incluyen ID de visitante, ECID, visitas ni datos de usuario único. Son datos de resumen agregados no vinculados con el visitante.
&#x200B;- Las variables reservadas no admiten la configuración del tipo de asignación o del tipo de caducidad, ya que no están vinculadas a un visitante.
&#x200B;- Los datos no se pueden unir con otros conjuntos de datos o dimensiones de Analytics de la forma que se puede en Customer Journey Analytics.
&#x200B;- Utilice la métrica **Solicitudes** para medir el volumen de tráfico real y de bots. No lo utilice de forma intercambiable con métricas basadas en visitas o visitas en cualquier otra parte del grupo de informes.

El conjunto exacto de campos disponibles debe confirmarse con la configuración de variables del grupo de informes una vez habilitado el conector.

### Responsabilidades

La configuración del conector entrante conlleva responsabilidades tanto para [Adobe](#adobe-managed-responsibilities) como para [usted como cliente](#customer-owned-responsibilities).

#### Responsabilidades gestionadas por Adobe

1. Detecta y confirma el reenvío de registros de CDN para cada sitio de Visibilidad de la marca incorporado.
2. Hace que las variables reservadas estén disponibles para el aprovisionamiento una vez que se confirme el reenvío de registro de BYOCDN.
3. Ejecuta el relleno de 90 días y la sincronización horaria en curso una vez que el conector está habilitado para un grupo de informes.

#### Responsabilidades de propiedad del cliente

1. Finalización de la incorporación de la Visibilidad de la marca y el reenvío de registros BYOCDN para cada sitio.
2. La confirmación de los datos se puede ver en el tablero de tráfico de la Visibilidad de la marca antes de activar el conector.
3. Selección del grupo de informes al que se conecta cada sitio de Visibilidad de la marca (un sitio por grupo de informes).
4. Habilitación del conector mediante el Administrador del grupo de informes.
5. Generar informes, segmentos o vistas de datos (cuando corresponda) que utilicen las variables reservadas que se enumeran en [Cómo funciona](#how-it-works).

### Antes de comenzar

Confirme lo siguiente antes de activar el conector:

&#x200B;- Ha completado la incorporación de Adobe Brand Visibility para el sitio al que desea conectarse.
&#x200B;- El reenvío de registros BYOCDN está configurado y confirmado para ese sitio (consulte [requisitos previos](#inbound-integration)).
&#x200B;- Se muestran datos en el tablero de tráfico de Adobe Brand Visibility Agent para ese sitio.
&#x200B;- Sabe a qué grupo de informes desea conectar el sitio.

Cada sitio de Adobe Brand Visibility se conecta exactamente a un grupo de informes. Si desea incluir datos de más de un sitio de Visibilidad de la marca, conecte cada sitio a un grupo de informes independiente.


### Habilitar el conector

El conector se activa y desactiva en el menú **Editar configuración** del grupo de informes.

Para abrir la configuración de Adobe Brand Visibility del grupo de informes:

1. Inicie sesión en Adobe Analytics.
1. Vaya a **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Seleccione el grupo de informes que desea conectar.
1. Seleccione **[!UICONTROL Editar configuración]**.
1. En el menú contextual, seleccione **[!UICONTROL Adobe Brand Visibility]**.

Para aprovisionar el conector:

1. Seleccione **Aprovisionar el conector de datos de Adobe Brand Visibility**.
1. Revise las dimensiones y métricas que se agregarán a este grupo de informes (enumeradas en [Cómo funciona](#how-it-works)).
1. En **Seleccionar sitio de Adobe Brand Visibility**, elija el sitio al que conectarse a este grupo de informes. Una vez conectado, los datos de resumen del sitio se sincronizan con este grupo de informes cada hora.
1. Seleccione **Habilitar**.

   Una vez activadas, estas variables no se pueden eliminar de este grupo de informes. Al habilitar el conector, se inicia un relleno de 90 días y se importan los últimos 90 días de datos de Adobe Brand Visibility en este grupo de informes.

   Antes de habilitar el conector, confirme que ha completado los pasos descritos en [Antes de comenzar](#before-you-start), esto incluye la verificación de que los datos ya se muestran en el panel de tráfico de Adobe Brand Visibility Agentic.

Una vez habilitado el conector, espere a que se complete el relleno inicial y la primera sincronización horaria. A continuación, confirme que las variables reservadas mencionadas en [Funcionamiento](#how-it-works) se rellenan en el grupo de informes. ver sección 8, paso 3).

### Desactivar el conector

>[!WARNING]
>
>Deshabilitar el conector es **irreversible**. Al deshabilitar esta opción, se detiene la sincronización horaria y se eliminan los datos históricos de Adobe Brand Visibility para este grupo de informes.

Para desactivar el conector:

1. Vaya a **Administración → Grupos de informes → Editar configuración → Adobe Brand Visibility**.
1. Seleccione **Anular el aprovisionamiento de Adobe Brand Visibility Data Connector**.
1. Confirme que el sitio de Adobe Brand Visibility que aparece en la lista es el que desea desconectar.
1. Seleccione **Deshabilitar**.
1. Reconozca la advertencia para confirmar.

Si solo desea pausar los informes temporalmente, no deshabilite el conector. Póngase en contacto con el equipo de su cuenta de Adobe para discutir las opciones para pausar la creación de informes antes de deshabilitarla.

### Configurar criterios de finalización

La integración entrante está lista para la creación de informes cuando se confirmen todas las siguientes opciones:

* Adobe Brand Visibility reenvía y recibe los registros de CDN para el sitio.
* Los datos se pueden ver en el tablero Tráfico de Adobe Brand Visibility Agent del sitio.
* El conector se ha habilitado para el grupo de informes deseado mediante el Administrador de grupos de informes.
* Se han completado el relleno inicial y al menos una sincronización por hora.
* Las variables reservadas en la sección 4 devuelven valores esperados en los informes.

### Procedimiento de verificación

El procedimiento de verificación consta de los siguientes pasos:

1. Confirme la preparación del sitio de Visibilidad de la marca y el registro de CDN:

   * Confirme el sitio o dominio exacto que desea conectar.
   * Confirme que los registros de CDN se reenvían para ese sitio y que la Visibilidad de la marca ha confirmado la recepción.
   * Confirme que los datos estén visibles en el tablero Tráfico del agente para ese sitio.

1. Confirme que el conector está activado:

   1. Vaya a **Administración → Grupos de informes → Editar configuración → Adobe Brand Visibility** para el grupo de informes de destino.
   1. Confirme que la página muestra el conector como habilitado y enumera el sitio de Visibilidad de la marca conectado.

1. Confirmar datos en informes:

   1. Abra Analysis Workspace (o el flujo de trabajo de creación de informes estándar) con el grupo de informes conectado.
   1. Cree una tabla o una visualización con la métrica **Solicitudes** desglosada por **Tipo de bot**.
   1. Confirme que aparece el volumen de solicitud para un intervalo de fechas reciente.
   1. Confirme las dimensiones **URL**, **Agente de usuario**, **Estado** y **Referente** que devuelven los valores esperados.

   La hora exacta requerida para que aparezcan los datos depende del relleno y la programación de sincronización descritos en [Habilitar el conector](#enable-the-connector).



### Resolución de problemas

Consulte los siguientes problemas y cómo solucionarlos.

| Problema | Solucionar problemas |
|---|---|
| El conector no se habilita o la lista de sitios está vacía. | Compruebe si:<ul><li>La incorporación de Adobe Brand Visibility al sitio ha finalizado.</li><li>El reenvío de registros BYOCDN está configurado y confirmado para el sitio.</li><li>Está trabajando en el grupo de informes correcto.</li><ul> |
| El conector está activado, pero no aparece ningún dato. | Compruebe si: <ul><li>Los datos están visibles en el tablero Tráfico de agente para el sitio conectado (si no es así, el problema está en el flujo ascendente de Analytics).</li><li>Ha pasado tiempo suficiente para el relleno inicial de 90 días y al menos una sincronización por hora.</li><li>: el intervalo de fechas seleccionado en el informe incluye un periodo después de habilitar el conector.</li></ul> |
| Los datos parecen incompletos o inesperados. | Compruebe si: <ul><li>No se espera que el grupo de informes reciba datos para un sitio de Visibilidad de la marca diferente (cada grupo de informes se conecta exactamente a un sitio).</li><li>Está leyendo la métrica **Solicitudes** en lugar de contar filas o visitas en cualquier otra parte del grupo de informes.</li><li>Las dimensiones que está viendo coinciden con la lista de la sección 4. Las eVars o los eventos no relacionados del mismo grupo de informes no forman parte de esta integración.</li></ul> |

>[!MORELIKETHIS]
>
>[Referencia de integración de Visibilidad de la marca /LMO](https://experienceleague.adobe.com/es/docs/analytics-platform/using/integrations/bv)
>[Referencia de reenvío de registro BYOCDN](https://experienceleague.adobe.com/es/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)

&#x200B;---

## Notas de redacción para documentos (no para publicación)

Esta sección es para revisión interna y debe eliminarse antes de publicar.

&#x200B;- **Source de verdad usado:** los nombres de campo, la lista de variables reservada y el flujo de trabajo del Administrador de grupos de informes provienen de [AN-468884](https://jira.corp.adobe.com/browse/AN-468884) (David Wardell, estado Nuevo a partir del 28 de agosto de 2026), que es más actual y más específico que la solicitud de documentación original [AN-449989](https://jira.corp.adobe.com/browse/AN-449989) (Rob In der, estado Nuevo). La copia de página para las pantallas de aprovisionamiento/desaprovisionamiento incorpora los refinamientos de redacción de la revisión interna del 28 de agosto de 2026 (`2026-08-28-an468884-abv-report-suite-ui-review.md`), que reemplazó la abreviatura &quot;ABV&quot; del ticket sin procesar por &quot;Adobe Brand Visibility&quot; en el texto orientado al cliente.
&#x200B;- **Discrepancia del conjunto de campos que se debe conciliar antes de la publicación:** La lista de dimensiones original de AN-449989 era Host, URL/Ruta de página, Proveedor de CDN, Agente de usuario y Tipo de bot de LLM, con una sola métrica de recuento de solicitudes de agente. La lista de variables reservadas real de AN-468884 es la dirección URL, el tipo de bot, el agente de usuario, el estado y el referente, con un solo evento de solicitudes. El host y el proveedor de CDN no están presentes como variables reservadas independientes en AN-468884; el estado es nuevo. Este borrador sigue AN-468884 como autorizado según el ticket de eng, pero ambos deben reconciliarse con Aaron Kern / David Wardell antes de que esto finalice, ya que los nombres de campo que los clientes ven pueden no coincidir con lo que los equipos de cuenta han descrito utilizando el idioma AN-449989 más antiguo.
&#x200B;- **Aún no se ha confirmado, no se indica como hecho en la versión publicada:**
  &#x200B;- Fecha exacta de la GA. AN-431416 lleva FixVersion H2 2026 (ventana de versión 2026-11-30) y está en estado de ejecución a partir del 01-09-2026; AN-468884 (implementación de variable reservada) y AN-449989 (este documento) siguen siendo nuevos. No publicar hasta que se envíe eng.
  &#x200B;- Si el tipo de asignación o el tipo de caducidad se suprimen completamente en las evars reservadas en producción. La revisión del 28 de agosto de 2026 indicó que un grupo de informes de prueba muestra actualmente estas evars con Asignación establecida en Más reciente (último), que puede ser un valor predeterminado que debe borrarse en lugar de confirmar el comportamiento final.
  &#x200B;- El punto final de la API de LLMO para enumerar sitios ABV por la organización de IMS (rellena el menú desplegable Selección de sitio) y la API de desprovisión/deshabilitación seguían pendientes de Joe Bass a partir del comentario del ticket del 2026-08-26.
  &#x200B;- La comparación exacta del recuento de campos de CJA. El ticket original de AN-449989 afirma que CJA tiene &quot;9 dimensiones adicionales&quot; y &quot;5 métricas adicionales&quot;, pero varias de ellas (Bloque de sesiones de LLM, Recuento de sesiones únicas de LLM, Recuento de duplicaciones de solicitudes de LLM) no se confirmaron para existir en el grupo de campos `cdn-requests-summary` entregado en la revisión del 18 de junio de 2026. Este borrador evita intencionadamente citar recuentos específicos en la comparación de CJA por ese motivo.
  &#x200B;- La cadencia de sincronización de esta ruta AA se indica aquí por hora, coincidiendo con el idioma de vale de AN-468884 (&quot;ejecutar sincronizaciones por hora&quot; / &quot;proceso de sincronización por hora&quot;). Esto no se ha validado de forma independiente para el comportamiento de las fuentes de datos AA de producción como se hacía con la cadencia de CJA.


## Integración saliente

Esta guía cubre únicamente la Visibilidad de la marca de entrada, que añade datos sobre el tráfico de bots y agentes automatizados a un grupo de informes de Analytics. En la documentación de integración publicada también se describe una dirección de salida en la que los datos de rendimiento de Analytics se ponen a disposición de la Visibilidad de la marca dentro del producto de Visibilidad de la marca. Esa dirección está fuera del ámbito de esta guía. Consulte el [documento de Visibilidad de la marca](https://experienceleague.adobe.com/es/docs/brand-visibility/using/resources/adobe-analytics-integration) para obtener más información sobre la integración saliente.