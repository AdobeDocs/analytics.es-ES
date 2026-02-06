---
description: Preguntas frecuentes sobre Advertising Analytics.
title: Preguntas más frecuentes sobre análisis de publicidad
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: e37b8f3e9508ebaf673c992c03064a43559fb9cf
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 10%

---

# Preguntas frecuentes 

## Acceso y derechos {#access}

+++ ¿Debo ser cliente de Adobe Advertising Cloud o Adobe Advertising Cloud (AMO) para acceder a esta funcionalidad?

No, esta funcionalidad está disponible para clientes que no sean de Advertising Cloud ni de AMO.

Los clientes de AMO pueden aprovechar la integración existente entre Analytics y AMO; no podrán utilizar Ad Analytics.

+++

+++ ¿Qué SKU de Adobe Analytics dan derecho a utilizar Advertising Analytics? 

Advertising Analytics está disponible para Adobe Analytics

* [Seleccionar](https://www.adobe.com/es/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/es/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/es/data-analytics-cloud/analytics/ultimate.html)

+++

+++ ¿Tengo que pagar un extra para usar Advertising Analytics? 

No, Advertising Analytics no incurre en ningún coste adicional si no está aprovisionado correctamente.

+++

+++ ¿Advertising Analytics cuenta para mi uso de llamadas al servidor?

No, Advertising Analytics utiliza un tipo de fuente de datos especial que no incurre en costes de llamadas al servidor.

+++

+++ Si ya utilizo Advertising Cloud/AMO, ¿puedo seguir utilizando la funcionalidad de Advertising Analytics?

Cualquier cuenta de motor de búsqueda compatible pasará a Advertising Analytics y se mostrará como de solo lectura. Todas las ediciones o actualizaciones deben gestionarse en Advertising Cloud/AMO.

+++

+++ Tengo el SKU correcto, pero no puedo acceder a Advertising Analytics, ¿por qué? 

Advertising Analytics solo está disponible para administradores de Adobe Analytics; sin embargo, los administradores pueden otorgar acceso a los usuarios que no sean administradores. Póngase en contacto con el administrador para obtener derechos de acceso.

+++

## Uso de Advertising Analytics {#using}

+++ ¿Qué cuentas de motor de búsqueda se incluyen en Advertising Analytics?

Las cuentas de motor de búsqueda incluyen Google Ads y Microsoft Advertising.

+++

+++ ¿Dónde debo ir para acceder a Advertising Analytics?

Después de iniciar sesión en Adobe Analytics, vaya a [!UICONTROL Admin]. A continuación, seleccione [!UICONTROL Advertising Analytics] para agregar las cuentas de motor de búsqueda.

+++

+++ ¿Cómo se recopilan y pasan los datos a Analytics? 

Advertising Analytics utiliza una serie de API personalizadas para pasar datos de los motores de búsqueda a Analytics a través de Adobe Advertising Cloud.

+++

+++ ¿Qué datos de búsqueda obtengo con esta integración? 

Obtendrá lo siguiente

* Impresiones
* Clics
* Costos
* Puntuación de calidad
* Posición promedio directamente de los motores de búsqueda, así como
* Instancias de ID de AMO (instancias de clic).

+++

+++ ¿Puedo desglosar mis datos de Advertising Analytics con otros datos de Analytics (métricas/dimensiones)? 

No, los datos de búsqueda sin procesar se incluirán como un conjunto de datos independiente. Sin embargo, existe una versión de instancias de los datos de clics que puede desglosarse con otros datos de Analytics.

+++

+++ ¿Cuál es la definición de los distintos indicadores de estado de mis cuentas (pendiente, activo, en pausa, etc.)? Cada uno de estos indicadores de estado identifica la fase del ciclo vital de la cuenta de cada motor de búsqueda. 

* [!UICONTROL Pendiente]
* [!UICONTROL En pausa] significa que la cuenta se configuró anteriormente pero que se puso en un estado inactivo.
* [!UICONTROL Activo] significa que la cuenta se ha configurado completamente y está extrayendo datos de búsqueda.

+++

+++ Estoy intentando asignar mis cuentas de Advertising Analytics a un grupo de informes específico, pero no está disponible en el modal del grupo de informes. ¿Por qué? 

Para poder asignar un grupo de informes a una cuenta de Advertising Analytics, el grupo de informes deseado debe estar [aprovisionado para los informes de Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Esto se realiza a través de una página de Administración independiente a la que se puede acceder desde: Administración > Grupos de informes > `[select report suite]` > Editar configuración > Configuración de Advertising Analytics.

+++

+++ ¿Es posible asignar un grupo de informes virtuales a una cuenta de Advertising Analytics? 

Los grupos de informes virtuales no recopilan datos, por lo que no puede asignar directamente una cuenta de Advertising Analytics a un grupo de informes virtuales. Sin embargo, puede asignar la cuenta de Advertising Analytics al grupo de informes principal del grupo de informes virtuales en el que desea ver los datos. Es posible que las métricas del motor de búsqueda (clic/coste/impresiones) no se muestren en el grupo de informes virtual a menos que incluya una condición &quot;o&quot; en la lógica del segmento basada en el ID de AMO (o en su clasificación). Ejemplo: Agregar “todas las visitas donde exista un ID de AMO” incluiría en el segmento las métricas del motor de búsqueda.

+++

+++ ¿Se pueden incluir las métricas de Advertising Analytics en el informe *Canales de mercadotecnia*? 

No, no se incluyen en el informe Canales de marketing.

+++

+++ ¿Cuándo se incorporan los datos de búsqueda a Analytics? 

Los datos de búsqueda se obtienen de los motores de búsqueda alrededor de las 6 a. m. (06:00) en la zona horaria del centro de datos de Analytics. Este es el momento en que los datos de AMO se recopilan y se insertan en el grupo de informes. A continuación, se convierten a la zona horaria del grupo de informes como parte del proceso de inserción de los datos en Analytics.

+++

+++ ¿Qué se puede *capturar antes del clic*? ¿Traemos impresiones, costo, posición promedio, etc.? ¿incluso sin el clic?

El ID de AMO registrará las métricas del motor de búsqueda: impresiones, costes, clics, posición media y puntuación de calidad media. Si no hay clics pero hay impresiones, los datos de puntuación de impresión/posición/calidad se enviarán a Analytics. Normalmente, si no hay clics, también no hay coste.

+++

+++ ¿A qué nivel se capturan estos datos? *¿Una visita? Visita individual?* 

Las métricas del motor de búsqueda se capturan en el nivel de la visita y se conectan al ID de AMO (y a sus clasificaciones). Son datos de resumen y no están conectados a visitas/visitantes. De este modo, las métricas del motor de búsqueda solo se pueden utilizar en segmentos que sean de ámbito de nivel de visita y que se basen en el ID de AMO (o en sus clasificaciones).

El ID de AMO también se captura en la página de aterrizaje de la visita para esa página (que la conecta con la visita/visitante) y persistirá en la fase posterior para obtener crédito por otras métricas de Analytics (hasta que caduque o se sobrescriba con un nuevo ID de AMO). Se incorpora completamente al conjunto de datos como cualquier otro eVar.

+++

+++ ¿Solo capturamos google.com o *versiones de países* (como google.co.uk, google.it, google.fr o google.de) también? 

La clasificación de la Plataforma de publicidad registra estos valores: &quot;Google AdWords&quot; y &quot;Bing Ads&quot;. Una recomendación habitual es incluir el código de país como parte del nombre de las campañas. A continuación, puede filtrarlas o segmentarlas (por ejemplo, si todas las campañas empiezan por códigodepaís_, el hecho de crear un segmento en el que las campañas (ID de AMO) empiecen por “UK_” solo le proporcionaría datos para el Reino Unido).

+++

+++ La métrica &quot;Coste de AMO&quot; es el coste pagado por cada palabra clave o anuncio según la información del motor de búsqueda. ¿Es coste neto o coste bruto? 

&quot;Coste de AMO&quot; es solo el coste pagado a los motores de búsqueda. No incluye tarifas de agencia ni de plataforma de optimización/gestión de búsquedas.

+++

+++ ¿Hay planes para incluir otros canales publicitarios como *Pantalla* o *Social*? 

No, actualmente no tenemos planes para estos otros canales en la hoja de ruta.

+++


## Seguimiento automático frente al manual {#section_7437C4698A6D482EB7ED94A948390119}

+++ Al configurar mi cuenta de Advertising, se indica que el *seguimiento automático* puede tener consecuencias no deseadas. ¿Qué tipo de consecuencias pueden ocurrir? 

El modo automático intenta anexar parámetros de URL al final de las plantillas de seguimiento/URL de destino en el formato correcto. Sin embargo, es su responsabilidad asegurarse de que los parámetros de URL añadidos se conserven correctamente en la página de aterrizaje final. El modo automático puede insertar palabras clave en la dirección URL de aterrizaje y es posible que el servidor web no admita palabras clave con caracteres especiales.

+++

+++ Si configuro el seguimiento manual o automático inicialmente, ¿puedo cambiar al otro modo de seguimiento más adelante? ¿Cuáles son las implicaciones? 

Sí, puede cambiar los modos de seguimiento, pero debe eliminar la lógica de seguimiento antigua antes de realizar el cambio. Esto puede provocar cierto tiempo de inactividad en el seguimiento el día en que se realiza el cambio (especialmente si se cambia de manual a automático). Como tal, recomendamos no cambiar a menos que sea absolutamente necesario.

* Cambio de manual a automático: elimine las adiciones manuales a las plantillas de seguimiento y, a continuación, cambie el conmutador de la IU de Advertising Analytics de manual a automático y guarde la configuración. Tenga en cuenta que el sistema puede tardar varias horas en rellenar los códigos de seguimiento automáticos.

* Cambio de automático a manual: actualice el cambio de manual a automático en la interfaz de usuario de configuración de Advertising Analytics y, a continuación, implemente los códigos de seguimiento manuales lo antes posible. Al implementar los códigos de seguimiento manuales, si ve los códigos de seguimiento automáticos en las plantillas de seguimiento del motor de búsqueda, elimínelos.

+++
