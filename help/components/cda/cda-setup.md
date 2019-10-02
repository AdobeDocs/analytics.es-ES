---
title: Configuración de análisis entre dispositivos
description: Obtenga información sobre cómo configurar Analytics entre dispositivos después de cumplir los requisitos previos.
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# Configuración de análisis entre dispositivos

> [!NOTE] La documentación de Análisis entre dispositivos está sujeta a cambios a medida que la función se desarrolla. Vuelva regularmente para ver las actualizaciones.

Una vez cumplidos todos los requisitos previos, siga los pasos siguientes para habilitar el análisis entre dispositivos. Debe pertenecer a un grupo de administradores de perfil de producto o tener privilegios de administrador en Adobe Analytics para seguir estos pasos.

> [!IMPORTANT] Todos los requisitos previos deben cumplirse antes de seguir estos pasos. Si no se cumplen todos los requisitos previos, la función no está disponible o no funcionará. Consulte Análisis [entre dispositivos](cda-home.md) para conocer los requisitos previos y las limitaciones.

## Elija el grupo de informes entre dispositivos que se habilitará para CDA

Cuando su organización está aprovisionada para utilizar CDA, usted elige qué grupo de informes utilizar. Esta opción se puede comunicar a través del administrador de cuentas de Adobe. A continuación, Adobe habilita el grupo de informes elegido para el procesamiento de CDA.

## Crear un grupo de informes virtuales entre dispositivos para ver la vista entre dispositivos

Los administradores con acceso para crear grupos de informes virtuales pueden crear grupos de informes virtuales CDA de la siguiente manera:

1. Vaya a [experience.adobe.com](https://experiencecloud.adobe.com) e inicie sesión con sus credenciales de Adobe ID.
2. Click the 9-grid icon at the top, then click Analytics.
3. Hover over Components at the top, then click Virtual Report Suites.
4. Haga clic en Agregar.
5. Enter a name for your virtual report suite, and ensure that the CDA-enabled report suite is selected.
6. Click the checkbox 'Enable Report Time Processing', which enables several more options including Cross-Device Analytics.
7. Click the checkbox 'Stitch User Visits Across Devices'.
8. Click Continue, finish configuring the virtual report suite, then click Save.

![CDA checkbox](assets/cda-checkbox.png)

## Additions and changes to cross-device virtual report suites

When Cross-Device Analytics is enabled on a virtual report suite, note the following changes:

* A new cross-device icon appears next to the virtual report suite name. This icon is exclusive to cross-device virtual report suites.
* New metrics labeled 'People' and 'Unique Devices' are available.
* The metric 'Unique Visitors' is not available, as it is replaced with People and Unique Devices.
* Al generar segmentos, el contenedor de segmentos 'Visitante' se reemplaza por un contenedor 'Persona'.

## The Compression calculated metric

La capacidad de los análisis entre dispositivos para unir dispositivos depende de una amplia variedad de factores. La eficacia de la capacidad de la función para unir datos se puede medir con una métrica calculada llamada compresión. Los factores que contribuyen a la compresión incluyen:

* Uso del gráfico de cooperación o del gráfico privado: En términos generales, las organizaciones que utilizan la cooperación entre dispositivos tienden a ver mejores tasas de compresión que las organizaciones que utilizan el gráfico privado.
* Velocidad de inicio de sesión: Cuantos más usuarios inicien sesión en el sitio, más podrá Adobe identificar y unir a los visitantes entre dispositivos. Los sitios con una tasa de inicio de sesión baja también tienen tasas de compresión bajas.
* Cobertura del ID de Experience Cloud: Solo se pueden vincular los visitantes con un ECID. Un porcentaje menor de visitantes que utilizan un ECID se correlaciona con tasas de compresión más bajas.
* Uso de varios dispositivos: Si los visitantes del sitio no utilizan varios dispositivos, puede ver tasas de compresión más bajas.
* Granularidad de informes: La compresión por día suele ser menor que la compresión por mes o año. Las posibilidades de que un individuo utilice varios dispositivos se reducen en un solo día en comparación con todo un mes. Segmentar, filtrar o utilizar dimensiones de desglose también puede mostrar una tasa de compresión más baja.

Para ver la compresión de su organización durante un período de tiempo determinado:

1. Haga clic en Espacio de trabajo en la parte superior y, a continuación, en 'Crear nuevo proyecto'.
2. Comience con un proyecto en blanco y, a continuación, haga clic en Crear.
3. Drag the Unique Devices metric onto the canvas area labeled 'Drop a Metric Here'.
4. Arrastre la métrica Personas al lienzo directamente a la derecha del encabezado de métrica Dispositivos únicos, de modo que las dos métricas estén una al lado de la otra.
5. Haga clic en el símbolo '`+`' al lado de las métricas disponibles a la izquierda para abrir el Creador de métricas calculadas.
6. Asigne esta métrica calculada la siguiente configuración:
   * Nombre: Compresión entre dispositivos
   * Formato:Porcentaje
   * Decimal Places: 2
   * Definición: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Haga clic en 'Agregar' en la esquina superior derecha del área de definición para agregar un número estático. Arrastre Personas y Dispositivos únicos desde la lista de métricas disponibles a la izquierda.
7. Haga clic en Guardar.
8. Arrastre la nueva métrica calculada al lienzo directamente a la derecha del encabezado de la métrica Personas, de modo que las tres métricas estén una al lado de la otra.
9. Opcional: El espacio de trabajo carga la dimensión Día de forma predeterminada. Arrastre una dimensión de fecha alternativa, como semana o mes, sobre la dimensión Día si desea una granularidad de tiempo diferente.
