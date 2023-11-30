---
description: Información general sobre el uso de los informes predeterminados en Analysis Workspace.
title: Uso de informes
feature: Analysis Workspace
role: User, Admin
source-git-commit: cf0c15c1b81a243e35fbdcf32b43a6ef4ada9649
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 85%

---

# Uso de informes generados previamente

Los informes creados previamente en Analysis Workspace proporcionan una visión rápida de los escenarios más comunes de creación de informes. A continuación se muestran algunos ejemplos de preguntas que puede responder con los informes pregenerados:

* La cantidad de personas que visitan el sitio
* La cantidad de los visitantes únicos (se cuentan solo una vez)
* La forma en la que llegaron al sitio (si siguieron un vínculo o llegaron directamente)
* Las palabras clave utilizadas por los visitantes para buscar el contenido del sitio
* El tiempo que los visitantes permanecieron en una página determinada o en todo el sitio
* Los vínculos en los que hicieron clic los visitantes y en qué momento salieron del sitio
* Los canales de marketing que son más eficaces para generar ingresos o eventos de conversión
* Cuánto tiempo emplearon en ver un vídeo
* Qué exploradores y dispositivos utilizaron para visitar el sitio

La siguiente información describe cómo acceder y utilizar informes pregenerados desde el [!UICONTROL Informes] en Analysis Workspace.

## Acceso y ejecución de un informe

1. En Analysis Workspace, seleccione la [!UICONTROL **Workspace**] pestaña.

1. Seleccionar [!UICONTROL **Informes**].

   ![Pestaña de informes](assets/view-prebuilt-reports.png)

1. En el campo de búsqueda, empiece a escribir el nombre del informe que desea buscar y, a continuación, selecciónelo en la lista de informes. También puede buscar en la lista de informes por propiedad, eVar y número de evento. <!-- still true? -->

   o

   Seleccione la categoría del informe que desea ver y, a continuación, seleccione el informe en la lista de informes.

   >[!TIP]
   >
   >   Para desplazarse por el menú con las teclas de dirección, presione la tecla de barra diagonal (/) y, a continuación, presione la tecla de dirección descendente. Pulse Intro para cargar el informe seleccionado.

Para obtener una lista de los informes disponibles, consulte la [Informes disponibles](#available-reports) más abajo.

## Guardar un informe {#use-reports}

Si sale de un informe después de realizar cambios, se le solicitará que guarde o descarte los cambios. Al guardar los cambios en un informe, se guarda el informe como un nuevo proyecto.

1. Vaya a la pestaña [!UICONTROL **Informes**].
1. Seleccione el informe que desee ver, por ejemplo, en [!UICONTROL **El más popular**], seleccione el informe [!UICONTROL **Páginas**].

   ![Informe de páginas](assets/pages-report.png)

1. El informe Páginas, tal como se muestra en Analysis Workspace, muestra dos [visualizaciones](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Gráfico de barras](/help/analyze/analysis-workspace/visualizations/bar.md) y [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) y una [Tabla de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). La métrica utilizada es Ocurrencias.
1. Realice una de las siguientes acciones:

   * Vea el informe.
   * Puede arrastrar uno o más segmentos a la zona de colocación de Segmento en la parte superior. Por ejemplo, arrastre el segmento [!UICONTROL **Clientes móviles**] y vea los resultados.
   * Para cambiar el intervalo de fecha, vaya al calendario en la parte superior derecha.
   * Añada desgloses de dimensión, arrastre otras métricas y, por lo general, personalice el informe según sus necesidades.

1. (Opcional) Guarde el informe como un proyecto seleccionando [!UICONTROL **Proyecto**] > [!UICONTROL **Guardar**].

   El informe se guarda como un proyecto nuevo; no modifica el informe existente. Para obtener más información sobre cómo guardar un informe como proyecto, consulte [Guardar proyectos](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

## Informes disponibles

La siguiente tabla contiene la lista completa de los informes pregenerados disponibles.

Algunos de los informes generados previamente más populares son Flujo, Visitas en el orden previsto, Canal de marketing e Informes en tiempo real.

| Elemento del menú | Informes bajo este elemento de menú |
| --- | --- |
| **[!UICONTROL Más populares]** | <ul><li>Tutorial de aprendizaje (plantilla del Espacio de trabajo preexistente)</li><li>Páginas (¿Cuáles son mis páginas principales?)</li><li>Vistas de página (¿Cuántas vistas de página estoy generando?)</li><li>Visitas (¿Cuántas visitas estoy teniendo?)</li><li>Visitantes (¿Cuántos visitantes estoy teniendo?)</li><li>Métricas clave (¿Cuál es el rendimiento de mis métricas más importantes?)</li><li>Secciones del sitio (¿Qué secciones de mi sitio generaron la mayor cantidad de vistas de página?))</li><li>Tiempo real (¿Cuáles son las tendencias en mi sitio y por qué?)</li><li>Página siguiente (¿Cuáles son las páginas siguientes a las que van mis visitantes?)</li><li>Página anterior (¿Cuáles son las páginas anteriores a las que se dirigieron mis visitantes?)</li><li>Campañas (¿Qué campañas están impulsando mis métricas clave?)</li><li>Productos (¿Qué productos están impulsando mis métricas clave?)</li><li>Canal de último contacto (¿Qué canal de último contacto tiene el mejor rendimiento?</li><li>Detalles del canal de último contacto (¿Qué canal de último contacto específico supera a los demás?)</li><li>Ingresos (¿Cómo van mis ingresos?)</li><li>Pedidos (¿Cómo van mis pedidos?)</li><li>Unidades (¿Cuántas unidades estoy vendiendo?)</li></ul> |
| **[!UICONTROL Participación]** | <ul><li>Métricas clave (¿Cuál es el rendimiento de mis métricas más importantes?)</li><li>Vistas de página (¿Cuántas vistas de página estoy generando?)</li><li>Páginas (¿Cuáles son mis páginas principales?)</li><li>Visitas (¿Cuántas visitas estoy teniendo?)</li><li>Visitantes (¿Cuántos visitantes estoy teniendo?)</li><li>Tiempo empleado por visita (¿Cuánto tiempo invierten mis usuarios por visita?)</li><li>Tiempo previo al evento (¿Cuánto tiempo dedican mis usuarios antes de un evento de éxito?)</li><li>Secciones del sitio (¿Qué secciones de mi sitio generaron la mayor cantidad de vistas de página?)</li><li>Consumo de contenido web (¿Qué contenido se consume más y resulta más atractivo para los usuarios?)</li><li>Consumo de contenido multimedia (¿Qué contenido se consume más y resulta más atractivo para los usuarios?)</li><li>Flujo de página siguiente y anterior (¿Cuáles son/fueron las rutas siguientes/anteriores de mis visitantes?)</li><li>Visita en orden previsto (¿Dónde veo la visita en orden previsto en mis propiedades digitales?)</li><li>Análisis entre dispositivos (Uso del análisis entre dispositivos en Analysis Workspace)</li><li>Retención web (¿Quiénes son mis usuarios más fieles y qué hacen?)</li><li>Consumo de audio multimedia (¿Cuáles son las tendencias y las principales métricas de consumo de audio?)</li><li>Actualización, frecuencia y lealtad de medios (¿Quiénes son mis lectores más fieles?)</li><li>Análisis de página > Recargas (¿Qué páginas generan la mayor cantidad de recargas?)</li><li>Análisis de página > Tiempo empleado en la página (¿Cuánto tiempo dedican mis usuarios a mis páginas?)</li><li>Entradas y salidas > Páginas de entrada (¿Cuáles son mis páginas de entrada principales?)</li><li>Entradas y salidas > Páginas de entrada originales (¿desde qué página entró mi visitante originalmente?)</li><li>Entradas y salidas > Visitas de página única (¿Qué páginas generaron la mayor cantidad de visitas de página única?)</li><li>Entradas y salidas > Páginas de salida (¿Cuáles son mis páginas de salida principales?)</li></ul> |
| **[!UICONTROL Conversión]** | <ul><li>Productos > Productos (¿Qué productos dirigen mis métricas clave?)</li><li>Productos > Rendimiento del producto (¿Qué productos tienen el mejor rendimiento?)</li><li>Productos > Categorías (¿Cuáles son las categorías de productos que tienen un mejor rendimiento?)</li><li>Carro de compras > Carros de compras (¿Cuántos usuarios agregaron un producto al carro de compras?)</li><li>Carro de compras > Vistas del carro de compras (¿Cuántas veces vieron mis visitantes sus carros de compras?)</li><li>Carro de compras > Adiciones al carro de compras (¿Con qué frecuencia los usuarios agregan un producto al carro de compras?)</li><li>Carro de compras > Eliminaciones del carro de compras (¿Con qué frecuencia eliminan los usuarios un producto de su carro de compras?)</li><li>Compras > Ingresos (¿Cómo van mis ingresos?)</li><li>Compras > Pedidos (¿Cómo van mis pedidos?)</li><li>Compras > Unidades (¿Cuántas unidades estoy vendiendo?)</li><li>[Magento: marketing y comercio](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#commerce)</li></ul> |
| **[!UICONTROL Audiencia]** | <ul><li>Métrica de personas (¿Cuántas personas interactúan con mi marca?)</li><li>Perfil del visitante > Información general sobre la ubicación (Qué ubicaciones son las que más utilizan los usuarios)</li><li>Perfil del visitante > Segmentación geográfica > Condados geográficos, Estados de EE. UU. geográficos, Regiones geográficas, Ciudades geográficas, DMA de EE. UU. geográfico (¿Desde qué lugares geográficos me visitan mis usuarios?)</li><li>Perfil del visitante > Idiomas (¿Qué idioma prefieren mis usuarios?)</li><li>Perfil del visitante > Zonas horarias (¿De qué zonas horarias me están visitando mis usuarios?)</li><li>Perfil del visitante > Dominios (¿Qué ISP utilizan los visitantes para acceder a mi sitio?)</li><li>Perfil del visitante > Dominios de nivel superior (¿Qué dominios conducen el tráfico a mi sitio?)</li><li>Perfil del visitante > Tecnología > Descripción general de la tecnología (¿Qué tecnologías utilizan los visitantes para acceder a mi sitio?)</li><li>Perfil del visitante > Tecnología > Exploradores, Tipo de explorador, Anchura del explorador, Altura del explorador (¿Qué explorador de qué empresa, versión de explorador, y ancho y alto utilizan las personas para acceder a mi sitio?)</li><li>Perfil del visitante > Tecnología > Sistema operativo, tipos de sistema operativo (¿Qué sistema operativo y qué versión usan mis visitantes?)</li><li>Perfil del visitante > Tecnología > Operador de telefonía móvil (¿Qué operadores de telefonía móvil utilizan los visitantes para acceder a mi sitio?)</li><li>Retención de visitantes > Frecuencia de retorno (¿Cuánto tiempo transcurre entre la visita actual del usuario y las visitas anteriores?)</li><li>Retención de visitantes > Visitas de retorno (¿Cuántas de mis visitas son usuarios recurrentes?)</li><li>Retención de visitantes > Número de visitas (Qué bloque de número de visitas genera la mayoría de mis métricas clave)</li><li>Retención de visitantes > Ciclo de ventas > Lealtad del cliente (¿A qué segmento de lealtad pertenecen mis usuarios?)</li><li>Retención de visitantes > Ciclo de ventas > Días antes de la primera compra (¿Cuántos días transcurrieron entre la primera visita de mis usuarios y su primera compra?)</li><li>Retención de visitantes > Ciclo de ventas > Días transcurridos desde la última compra (¿Cuántos días han transcurrido entre la visita actual de mis usuarios y la última compra?) )</li><li>Retención de visitantes > Móvil > Dispositivos y tipos de dispositivos (¿Qué dispositivos y tipos de dispositivos utilizan mis visitantes?)</li><li>Retención de visitantes > Móvil > Fabricante (¿Qué fabricante de dispositivo móvil usan mis visitantes?)</li><li>Retención de visitantes > Móvil > Tamaño, altura y anchura de la pantalla (¿Qué tamaño/altura/anchura de la pantalla móvil tienen mis visitantes?)</li><li>Retención de visitantes > Móvil > [Uso de aplicaciones móviles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#mobile)</li><li>Retención de visitantes > Móvil > [Recorridos de aplicaciones móviles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#mobile)</li><li>Retención de visitantes > Móvil > [Métricas de aplicaciones móviles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#mobile)</li><li>Retención de visitantes > Móvil > [Mensajería de aplicaciones móviles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#mobile)</li><li>Retención de visitantes > Móvil > [Rendimiento de las aplicaciones móviles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#mobile)</li><li>Retención de visitantes > Móvil > [Retención de aplicaciones móviles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#mobile)</li></ul> |
| **[!UICONTROL Adquisición]** | <ul><li>Canales de marketing > Canal de primer contacto, Detalles de canal de primer contacto (¿Qué canal de primer contacto y qué canal de primer contacto específico está teniendo el mejor rendimiento?)</li><li>Canales de marketing > Primer canal, Detalle del último canal (¿Qué canal de último contacto y qué canal de último contacto específico está teniendo el mejor rendimiento?)</li><li>Campañas > Campañas (¿Qué campañas están impulsando mis métricas clave?)</li><li>Campañas > Rendimiento de la campaña (¿Qué campañas consiguen el máximo de los ingresos?)</li><li>Campañas > Código de seguimiento (¿Qué códigos de seguimiento de campaña funcionan mejor?)</li><li>[Adquisición web](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#web)</li><li>[Adquisición móvil](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#mobile)</li><li>[Advertising Analytics: búsqueda de pago](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=es#advertising)</li><li>Palabras clave de búsqueda: todas, pagadas, naturales (¿Qué palabras clave de búsqueda y palabras clave de búsqueda pagada/natural impulsan mejor mis métricas clave?)</li><li>Motores de búsqueda: todos, pagados, naturales (¿Qué motores de búsqueda y motores de búsqueda natural/pagada impulsan mejor mis métricas clave?)</li><li>Clasificación de todas las páginas de búsqueda (¿De qué página de búsqueda están visitando mis usuarios?)</li><li>Dominios de referencia (¿Qué dominios dirigen tráfico a mi sitio?)</li><li>Dominios de referencia originales (¿Cuál fue el primer dominio en el que se encontraban los usuarios antes de visitar mi sitio?)</li><li>Remitentes del reenvío (¿En qué URL estaban mis usuarios antes de hacer clic en mi sitio?)</li><li>Tipos de remitente del reenvío (¿A qué categoría pertenecen mis URL de referencia?)</li></ul> |
