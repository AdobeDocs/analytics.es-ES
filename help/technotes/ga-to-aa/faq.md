---
title: Preguntas frecuentes
description: Conozca las respuestas a las preguntas más frecuentes sobre el cambio desde una plataforma de terceros a Adobe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 66%

---


# Preguntas frecuentes

**¿Cómo puedo migrar mis datos históricos desde mi plataforma de terceros a Adobe Analytics?**

Cada plataforma de Analytics tiene diferentes formas de recopilar, gestionar y almacenar datos. En lugar de migrar datos históricos, Adobe recomienda establecer una fecha de corte clara para empezar a recopilar y utilizar datos en Adobe Analytics. Las fechas de corte más frecuentes utilizadas son el comienzo de un año fiscal, el comienzo de un año natural o el comienzo de un mes natural. Si los usuarios desean ver los datos históricos, pueden iniciar sesión en la plataforma de terceros para obtener cualquier dato histórico necesario.

Si su organización insiste en tener datos históricos transferidos a Adobe, póngase en contacto con el administrador de cuentas de su organización. Un consultor de implementación puede trabajar con su organización para traducir una exportación de datos de Google Analytics a una fuente de datos que los servidores de recopilación de datos de Adobe puedan ingerir.

Adobe no recomienda la portabilidad de datos históricos, ya que se trata de un proceso complejo y con un coste elevado para su organización. También es complicado trasladar la identificación del visitante a Adobe, ya que la información del visitante se almacena en diferentes cookies y formatos entre plataformas.

**Estoy acostumbrado a un menú desplegable de segmentación en muchos de mis informes. How can I recreate that in[!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. En un proyecto de Workspace:

1. Utilice Ctrl+clic (Windows) o Cmd+clic (Mac) en los componentes que desee incluir en la lista desplegable. No está limitado solo a segmentos; cualquier componente se puede incluir en un filtro desplegable.
2. Arrastre el grupo de componentes al espacio de trabajo “Colocar un segmento aquí”. Antes de soltarlo, mantenga pulsada la tecla Mayús.

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**Estoy acostumbrado a hacer clic en un elemento de dimensión para ver una exploración en profundidad. ¿Cómo puedo replicar ese sencillo flujo de trabajo en Analysis Workspace?**

Los elementos de dimensión del [!UICONTROL Analysis Workspace] también tienen un flujo de trabajo de desglose sencillo. Acceda a ella haciendo clic con el botón derecho en lugar de hacer clic con el botón izquierdo. Right-click on a dimension item, click **[!UICONTROL Breakdown], then select the desired component. Puede aplicar el mismo desglose a varios elementos de dimensión mediante ctrl+clic (Windows) o cmd+clic (Mac) en cada valor.
