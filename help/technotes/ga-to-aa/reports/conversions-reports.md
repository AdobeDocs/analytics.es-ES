---
title: Informes de conversión en Adobe Analytics
description: Obtenga información sobre el uso de los informes de conversión en Adobe Analytics.
feature: Third-party Integration
exl-id: 315b7dc0-1cd9-4beb-8203-88e205375f84
TQID: https://experienceleague.adobe.com/nQEJ6fa-AOUAe3jg3sOpVaGWY1f7u27-SzfyWCrgykg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1057
ht-degree: 100%

---

# Informes de conversión

Una “conversión” es una acción llevada a cabo por un visitante en el sitio y que se traduce directamente en los indicadores clave de la organización. Los informes de conversión muestran detalles sobre la conversiones realizadas por los visitantes.

En esta página se da por hecho que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios de Google Analytics](create-report.md) si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Informes de objetivos

Los objetivos proporcionan a los usuarios de Google Analytics una forma de definir la conversión de un sitio web. Son el modo predeterminado de crear canales, flujo de comportamiento inverso, embudos multicanal y atribución. Los objetivos de Google Analytics no son retroactivos y solo se pueden configurar en la página de administración. Además, se basan únicamente en una página, evento, tiempo empleado o número promedio de páginas.

En Adobe Analytics, el concepto de objetivo no es obligatorio porque las métricas se pueden aplicar en cualquier contexto. Siempre que la implementación incorpore los eventos que desee rastrear, puede modificar cualquier informe de conversión y obtener resultados de inmediato sobre los datos históricos.

### Visualización de embudo

El informe de visualización de embudo ayuda a los analistas a centrarse en una serie concreta de pasos necesarios para la conversión. Por ejemplo: antes de realizar una compra, un visitante que se encuentra en un sitio de comercio electrónico tendría que acceder al carro de compra, a la página de facturación y envío, a la página de pago y a la página de revisión de pedidos.

En Analysis Workspace, estos datos se pueden ver mediante la Visualización de abandonos.

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de abandonos al espacio de trabajo sobre la tabla de forma libre
2. Haga clic en el icono de componentes de la izquierda y, a continuación, busque la dimensión **Páginas**.
3. Haga clic en el icono de flecha junto a la dimensión Páginas para mostrar los valores de la página. Los elementos de dimensión aparecen en color amarillo.
4. Busque la página que servirá como primer punto de contacto y arrástrela al espacio denominado “Agregar punto de contacto” en la visualización.
5. Continúe añadiendo los puntos de contacto deseados arrastrando los valores de página a la visualización.

La visualización de abandonos no se limita solo a la dimensión Páginas. Cualquier dimensión, métrica o segmento puede utilizarse para adaptar el informe de abandonos a las necesidades de la organización.

![Visualización de abandonos](/help/technotes/ga-to-aa/assets/fallout.png)

## Informes de comercio electrónico

Los informes de comercio electrónico los suelen utilizar los sitios en los que se venden productos o servicios, para medir los pedidos y los ingresos que generan los artículos. Esta característica está disponible en Adobe Analytics y se conoce como Informes de productos.

Tanto los informes de comercio electrónico de Google Analytics como los informes de productos de Adobe Analytics necesitan cambios de implementación personalizados para su uso. Consulte la dimensión [Productos](/help/components/dimensions/product.md) en la guía de usuario de componentes para obtener más información.

## Informes de embudo multicanal

Los informes de embudo multicanal proporcionan datos adicionales del canal de marketing aparte de los que aportan los informes de adquisición. Estos informes se centran en mostrar cómo se convierten los visitantes, en lugar de en cómo llegan al sitio.

>[!NOTE]
>
> El uso de informes multicanal en Adobe Analytics necesitan tanto la configuración de los canales de marketing como una implementación personalizada para dar cabida a la variable de productos y al evento de compra. Adobe recomienda trabajar con un consultor de implementación si estas funciones aún no están configuradas para su grupo de informes.

### Multicanal: conversiones asistidas

Las conversiones asistidas muestran el número de veces que cada canal ayudó con una conversión. En Analysis Workspace, se puede utilizar la métrica **Asistencia para pedidos**.

1. En el menú Componentes, localice la dimensión **Canal de marketing** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre la métrica **Asistencia para pedidos** sobre el encabezado de métrica **Ocurrencias** creado automáticamente para reemplazarla. Se pueden arrastrar métricas adicionales al espacio de trabajo.

### Varios canales: rutas de conversión principales

El informe de rutas de conversión principales muestra las principales rutas de canales que sigue un usuario antes de realizar la conversión. Analysis Workspace utiliza un informe de flujo para visualizar las rutas de conversión principales.

1. Haga clic en el icono Paneles, a la izquierda, y arrastre un panel Atribución sobre la tabla de forma libre.
2. Haga clic en el icono Componentes, a la izquierda, localice la dimensión **Canal de marketing** y arrástrela al cuadro denominado “Agregar dimensión”.
3. Busque el evento de conversión deseado en Métricas (por ejemplo: Pedidos) y arrástrelo al cuadro denominado “Agregar métrica”. Tenga en cuenta que las métricas calculadas no son compatibles con el panel Atribución.
4. Haga clic en Crear.
5. En el informe resultante, busque la visualización “Flujo de canal”. Este flujo muestra las rutas principales que siguió un visitante antes de realizar una compra.

Esta visualización de flujo es interactiva. Haga clic en cada canal para expandir el flujo en cualquier dirección.

![Visualización de flujo](/help/technotes/ga-to-aa/assets/flow.png)

### Varios canales: retraso

El informe de retraso muestra la cantidad de días que tardó un visitante en realizar la conversión en el sitio. En Analysis Workspace, estos datos están disponibles mediante la dimensión **Días antes de la primera compra**. Solo está disponible en el contexto de un evento de compra correctamente implementado.

1. En el menú Componentes, localice la dimensión **Días antes de la primera compra** y arrástrela al área grande de la tabla de forma libre denominada “Colocar una dimensión aquí”.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Adobe recomienda utilizar las métricas **Pedidos**, **Unidades** o **Ingresos** con esta dimensión.

Para otros tipos de conversiones, como los eventos personalizados, está disponible la dimensión **Tiempo previo al evento**. Esta muestra la cantidad de minutos que tardó un visitante en desencadenar el evento dentro de la visita.

1. En el menú Componentes, localice la dimensión **Tiempo previo al evento** y arrástrela al área grande de la tabla de forma libre denominada “Colocar una dimensión aquí”.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Adobe recomienda utilizar esta dimensión junto con eventos personalizados o eventos de compra.

### Varios canales: longitud de ruta

El informe de longitud de ruta muestra la cantidad de canales involucrados antes de un evento de conversión. En Analysis Workspace, el panel Atribución contiene estos datos en una de sus visualizaciones.

1. Haga clic en el icono Paneles, a la izquierda, y arrastre un panel Atribución sobre la tabla de forma libre
2. Haga clic en el icono Componentes, a la izquierda, localice la dimensión **Canal de marketing** y arrástrela al cuadro denominado “Agregar dimensión”.
3. Busque el evento de conversión deseado en Métricas (por ejemplo: Pedidos) y arrástrelo al cuadro denominado “Agregar métrica”. Tenga en cuenta que las métricas calculadas no son compatibles con el panel Atribución.
4. Haga clic en Crear.
5. En el informe resultante, localice la visualización “Puntos de contacto por recorrido”. Este histograma muestra la cantidad de canales que un visitante utilizó antes de realizar una compra.
