---
description: Los eventos de éxito son acciones de las que se puede llevar un seguimiento. Usted determina lo que es un evento de éxito. Por ejemplo, si un visitante compra un artículo, el evento de compra puede considerarse un evento de éxito..
keywords: evento
title: Resumen de los eventos de éxito
feature: Herramientas de administración
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 100%

---

# Resumen de los eventos de éxito

Los eventos de éxito son acciones de las que se puede llevar un seguimiento. Usted determina lo que es un evento de éxito. Por ejemplo, si un visitante compra un artículo, el evento de compra puede considerarse un evento de éxito..

Acceda a la página Eventos de éxito en la configuración del grupo de informes:

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en el botón de 9 cuadrículas en la parte superior y, a continuación, haga clic en [!UICONTROL Analytics].
3. Vaya a [!UICONTROL Administración] > [!UICONTROL Grupos de informes]
4. Seleccione el grupo de informes deseado y, a continuación, vaya a [!UICONTROL Editar configuración] > [!UICONTROL Conversión] > [!UICONTROL Eventos de éxito].
5. Busque el evento deseado y modifique el cuadro desplegable [!UICONTROL Registro de un evento único] a [!UICONTROL Registrar una vez por visita] o [!UICONTROL Usar ID de evento].

Existen muchas clases de eventos de éxito que varían en función del tipo de sitio web. Algunos ejemplos son:

* **Comercial**: vista de producto, cierre de compra, compra
* **Medios**: suscripción, registro en concurso, vista de página, vista de vídeo
* **Finanzas**: envío de solicitudes, inicio de sesión, uso de herramientas de autoservicio
* **Viajes**: reserva (compra), campaña interna (pulsación), búsqueda (precio de itinerario)
* **Telecomunicaciones**: compra, posibles clientes, uso de herramientas de autoservicio
* **Alta tecnología**: descarga de documentos técnicos, RFP, finalización de formularios, solicitudes de asistencia
* **Automoción**: envío de posible cliente, solicitar presupuesto, descarga de folletos

La variable [s.events](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/page-vars/events/event-serialization.html) define un evento de éxito.

## Página Eventos de éxito: descripciones {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Eventos de éxito]**.

La página Eventos de éxito permite configurar las variables de evento que se utilizan en un sitio. Pueden agregarse hasta 1000 eventos de éxito. Los eventos 81-1000 solo funcionan si se encuentran en código H22 o posterior.

| Elemento | Descripción |
|--- |--- |
| Evento | El nombre original del evento. |
| Nombre | Utilice nombres descriptivos para los eventos de éxito de su sitio. Por ejemplo, si evento1 se utiliza para realizar un seguimiento de los registros, cambie el nombre aquí para que evento1 se represente como la medida &quot;Registros&quot; en todos los informes de conversión. |
| Tipo | El tipo que seleccione determinará si el evento es de contador (estándar), numérico o de moneda. Los eventos numéricos y de moneda permiten incrementar las métricas en más de uno.  Los eventos de contador se utilizan para registrar un evento en un momento determinado, mientras que los de moneda registran un número decimal, como los impuestos y el transporte. Tras su recepción, el valor que se pasa a los eventos de moneda se convierte de la moneda específica de la página a la moneda básica del grupo de informes. Para obtener más detalles sobre el cómo utilizar los eventos de moneda, el usuario debe ponerse en contacto con un representante de Adobe. Los eventos numéricos se utilizan para generar informes sobre números que no representan monedas, como los números de cupones que se utilizan en los pedidos. Los eventos de moneda se utilizan para llevar a cabo el seguimiento de los cobros de impuestos y transporte. Los eventos que se utilicen en el tipo estándar de las Fuentes de datos deben ser eventos numéricos o de moneda. |
| Polaridad | La polaridad de métrica le permite indicar si Adobe Analytics debe considerar el aumento de un evento personalizado determinado (métrica) como positivo o negativo. Permitirá a Adobe Analytics mostrar indicadores de dirección (flechas) para añadir contexto en diversas métricas (por ejemplo, comparaciones de una semana a otra.  Ejemplo: si &quot;Errores enviados&quot; sube de una semana a otra, ¿Adobe Analytics debe considerarlo positivo o negativo? Un aumento de los registros de correo electrónico es probablemente positivo. Sin embargo, un aumento de los errores de envío de formulario es probablemente negativo.  En Analysis Workspace, la polaridad se aplica al formato condicional de Tabla improvisada, a las visualizaciones de Cambio de resumen y al esquema de colores Positivo y Negativo de la visualización de Mapa. |
| Descripción | Una breve descripción del propósito y el uso del evento. |
| Registro de un evento único | **Registrar una vez por visita**: vincula el evento determinado al periodo de sesiones del visitante. Se omiten los recuentos posteriores de un evento determinado en la misma visita. Este tipo de serialización de eventos no requiere ningún cambio de implementación.<br>**Usar ID de evento:** vincula el evento determinado a un ID personalizado. Se omiten los recuentos posteriores de un evento determinado con el mismo ID de evento. Este tipo de serialización de eventos requiere un ID personalizado en las visitas para anular la duplicación de valores. Consulte [Serialización de ID de eventos](../../../implement/vars/page-vars/events/event-serialization.md) en la guía de usuario sobre implementación. |
| Participación | Otorga crédito de atribución completo a todos los elementos de dimensión de la visita. |
| Advertencia (evento de moneda) | Cuando se cambia el tipo de un evento de moneda, un mensaje indica que los datos históricos no se encuentran disponibles en los informes.  Los distintos tipos de eventos utilizan tablas de datos independientes y no pueden utilizarse de forma simultánea. Algunos datos históricos pueden restaurarse si el usuario revierte el tipo de evento. No obstante, no se encontrarán disponibles los datos recopilados tras el cambio inicial. Para cambiar un tipo de evento debe prestarse gran atención. |
