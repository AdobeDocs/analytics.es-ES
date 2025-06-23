---
description: Los eventos de éxito son acciones de las que se puede llevar un seguimiento. Usted determina lo que es un evento de éxito. Por ejemplo, si un visitante compra un artículo, el evento de compra podría considerarse un evento de éxito.
keywords: evento
title: Resumen de los eventos de éxito
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 54%

---

# Eventos de éxito

Los eventos de éxito (también conocidos como eventos de conversión o eventos personalizados) son acciones de las que se puede realizar un seguimiento. Usted determina lo que es un evento de éxito. Por ejemplo, si un visitante compra un artículo, el evento de compra podría considerarse un evento de éxito.

Para ver un vídeo de información general sobre los eventos de éxito, consulte [Introducción a los eventos de conversión](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events) en la guía de tutoriales de Analytics.

## Ejemplos de eventos de éxito

Existen muchas clases de eventos de éxito que varían en función del tipo de sitio web. Algunos ejemplos son:

* **Comercial**: vista de producto, cierre de compra, compra
* **Medios**: suscripción, registro en concurso, vista de página, vista de vídeo
* **Finanzas**: envío de solicitudes, inicio de sesión, uso de herramientas de autoservicio
* **Viajes**: reserva (compra), campaña interna (pulsación), búsqueda (precio de itinerario)
* **Telecomunicaciones**: compra, posibles clientes, uso de herramientas de autoservicio
* **Alta tecnología**: descarga de documentos técnicos, RFP, finalización de formularios, solicitudes de asistencia
* **Automoción**: envío de posible cliente, solicitar presupuesto, descarga de folletos

La variable [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=es) define un evento de éxito.

## Configurar eventos de éxito

Puede configurar las variables de Evento que se usan en el sitio. Pueden agregarse hasta 1000 eventos de éxito. Los eventos 81-1000 solo funcionan si se usa código H22 o posterior.

Para configurar eventos de éxito:

1. En Adobe Analytics, seleccione **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Seleccione el grupo de informes donde desee configurar los eventos de éxito.
1. Seleccione **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Eventos de éxito]**.

   ![Resultado](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. En la columna [!UICONTROL **Evento**], identifique el nombre del evento que desea usar como evento de éxito.

1. En la columna **[!UICONTROL Nombre]**, active la casilla que hay junto al elemento para habilitar la edición y, a continuación, especifique el nombre que desee.

   Utilice nombres descriptivos para los eventos de éxito de su sitio. Por ejemplo, si evento1 se utiliza para realizar un seguimiento de los registros, cambie el nombre aquí para que evento1 se represente como la medida &quot;Registros&quot; en todos los informes de conversión.

1. En la columna **[!UICONTROL Type]**, active la casilla que hay junto al elemento para habilitar la lista desplegable y, a continuación, seleccione el tipo que desee.

   >[!IMPORTANT]
   >
   >Tenga en cuenta lo siguiente al cambiar el tipo de evento:<ul><li>Puede cambiar el tipo de evento entre contador y numérico sin perder el acceso a los datos capturados anteriormente.</li><li>Al cambiar los tipos de eventos a o desde un evento de moneda, se muestra un mensaje que indica que los datos históricos no están disponibles en los informes. Los distintos tipos de eventos utilizan tablas de datos independientes y no pueden utilizarse de forma simultánea. Algunos datos históricos pueden restaurarse si el usuario revierte el tipo de evento. Sin embargo, no estarán disponibles los datos recopilados tras el cambio inicial.</li></ul>

   El tipo que seleccione determina si el evento es de contador (estándar), numérico o de moneda. <p>Los eventos de contador se utilizan para registrar un evento a tiempo.</p><p>Los eventos numéricos se utilizan para generar informes sobre números que no representan monedas, como los números de cupones que se utilizan en los pedidos.</p> <p>Los eventos monetarios registran un número decimal, como impuestos o envíos. Tras su recepción, el valor que se pasa a los eventos de moneda se convierte de la moneda específica de la página a la moneda básica del grupo de informes. Los eventos de moneda se utilizan para llevar a cabo el seguimiento de los cobros de impuestos y transporte. Para obtener más detalles sobre el cómo utilizar los eventos de moneda, el usuario debe ponerse en contacto con un representante de Adobe.<p>Los eventos numéricos y de moneda permiten incrementar las métricas en más de uno.</p><p>Los eventos que se utilicen en el tipo estándar de las Fuentes de datos deben ser eventos numéricos o de moneda.</p>

1. En la columna **[!UICONTROL Polaridad]**, seleccione la casilla de verificación y, a continuación, elija en el menú desplegable si una tendencia al alza para esta métrica es positiva o negativa.

   esto le permite indicar si Adobe Analytics debe considerar el aumento de un evento personalizado determinado (métrica) como positivo o negativo. Activa indicadores de dirección (flechas) para añadir contexto en varias métricas (por ejemplo, comparaciones de una semana a otra).  Ejemplo: si &quot;Errores enviados&quot; sube de una semana a otra, ¿Adobe Analytics debe considerarlo positivo o negativo? Un aumento de los registros de correo electrónico es probablemente positivo. Sin embargo, un aumento de los errores de envío de formulario es probablemente negativo.  En Analysis Workspace, la polaridad se aplica al formato condicional de Tabla de forma libre, a las visualizaciones de Cambio de resumen y al esquema de colores Positivo y Negativo de la visualización de Mapa.

1. En la columna **[!UICONTROL Visibilidad]**, seleccione la casilla de verificación y, a continuación, elija en el menú desplegable si desea ocultar las métricas (integradas), los eventos personalizados y los eventos incorporados en el menú, los selectores de métricas, el Creador de métricas calculadas y el Generador de segmentos.

   Esta configuración no afecta a la recopilación de datos de esa métrica o evento. Solo afecta a su visibilidad en la interfaz de usuario, como se indica a continuación:

   Las configuraciones disponibles son las siguientes:

   | Configuración | Visible en | No visible en |
   |---------|----------|---------|
   | [!UICONTROL **Visible en todas partes**] | <ul><li>Analysis Workspace</li><li>Generador de segmentos</li><li>Creador de métricas calculadas</li></ul> | N/A |
   | [!UICONTROL **Generadores**] | <ul><li>Generador de segmentos</li><li>Creador de métricas calculadas</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Oculto en todas partes**] | N/A | <ul><li>Analysis Workspace</li><li>Generador de segmentos</li><li>Creador de métricas calculadas</li></ul> |

1. En la columna [!UICONTROL **Descripción**], active la casilla de verificación y, a continuación, proporcione una descripción.
1. En la columna [!UICONTROL **Registro de eventos únicos**], active la casilla de verificación y, a continuación, elija en el menú desplegable si desea registrar siempre el evento.

   Las opciones disponibles son las siguientes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Registrar Una Vez Por Visita**] | Vincula el evento determinado a la sesión del visitante. Se omiten los recuentos posteriores de un evento determinado en la misma visita. Este tipo de serialización de eventos no requiere ningún cambio de implementación. |
   | [!UICONTROL **Usar ID de evento**] | Vincula el evento determinado a un ID personalizado. Se omiten los recuentos posteriores de un evento determinado con el mismo ID de evento. Este tipo de serialización de eventos requiere un ID personalizado en las visitas para anular la duplicación de valores. Consulte [Serialización de ID de eventos](/help/implement/vars/page-vars/events/event-serialization.md) en la guía de usuario sobre implementación. |

1. En la columna [!UICONTROL **Participación**], active la casilla de verificación y, a continuación, elija si desea habilitar o deshabilitar la participación. Cuando se habilita, otorga crédito de atribución completo a todos los elementos de dimensión de la visita.

   >[!NOTE]
   >
   >Puede habilitar la participación de hasta un máximo de 100 eventos personalizados. Una vez superada esa cifra, puede crear métricas de participación en el creador [Métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md).

1. Seleccione **[!UICONTROL Guardar]**.
