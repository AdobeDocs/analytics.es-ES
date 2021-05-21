---
title: Preguntas frecuentes
description: Conozca las respuestas a las preguntas más frecuentes sobre el cambio desde una plataforma de terceros a Adobe.
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '403'
ht-degree: 100%

---

# Preguntas frecuentes

**¿Cómo puedo migrar mis datos históricos de mi plataforma de terceros a Adobe Analytics?**

Cada plataforma de Analytics tiene diferentes formas de recopilar, gestionar y almacenar datos. En lugar de migrar datos históricos, Adobe recomienda establecer una fecha de corte clara para empezar a recopilar y utilizar datos en Adobe Analytics. Las fechas de corte más frecuentes utilizadas son el comienzo de un año fiscal, el comienzo de un año natural o el comienzo de un mes natural. Si los usuarios desean ver los datos históricos, pueden iniciar sesión en la plataforma de terceros para obtener cualquier dato histórico necesario.

Si su organización insiste en tener datos históricos transferidos a Adobe, póngase en contacto con el administrador de cuentas de su organización. Un consultor de implementación puede trabajar con su organización para traducir una exportación de datos de Google Analytics a una fuente de datos que los servidores de recopilación de datos de Adobe puedan ingerir.

Adobe no recomienda la portabilidad de datos históricos, ya que se trata de un proceso complejo y con un coste elevado para su organización. También es complicado trasladar la identificación del visitante a Adobe, ya que la información del visitante se almacena en diferentes cookies y formatos entre plataformas.

**Estoy acostumbrado a un menú desplegable de segmentación en muchos de mis informes. ¿Cómo puedo recrear esta situación en [!UICONTROL Analysis Workspace]?**

Los filtros desplegables son una funcionalidad flexible y práctica de [!UICONTROL Analysis Workspace] que permite desglosar una segmentación. En un proyecto de Workspace:

1. Utilice Ctrl+clic (Windows) o Cmd+clic (Mac) en los componentes que desee incluir en la lista desplegable. No está limitado solo a segmentos; cualquier componente se puede incluir en un filtro desplegable.
2. Arrastre el grupo de componentes al espacio de trabajo “Colocar un segmento aquí”. Antes de soltarlo, mantenga pulsada la tecla Mayús.

Los usuarios que accedan a este proyecto de [!UICONTROL Workspace] pueden utilizar el desplegable para aplicar segmentos y otros componentes al proyecto. Consulte [Información general sobre paneles](/help/analyze/analysis-workspace/c-panels/panels.md) en la guía de herramientas de Adobe Analytics para obtener más información.

**Estoy acostumbrado a hacer clic en un elemento de dimensión para ver la navegación por jerarquía. ¿Cómo puedo replicar ese sencillo flujo de trabajo en Analysis Workspace?**

Los valores de dimensión en [!UICONTROL Analysis Workspace] también tienen un flujo de trabajo de desglose sencillo. Puede acceder a él haciendo clic con el botón derecho en lugar de hacer clic con el botón izquierdo. Haga clic con el botón derecho en un elemento de dimensión, haga clic en **[!UICONTROL Desglose] y seleccione el componente deseado. Puede aplicar el mismo desglose a varios elementos de dimensión pulsando Ctrl+clic (Windows) o Cmd+clic (Mac) en cada valor.
