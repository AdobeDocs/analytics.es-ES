---
title: Configuración de análisis entre dispositivos
description: Aprenda a configurar Analytics entre dispositivos después de cumplir los requisitos previos.
translation-type: tm+mt
source-git-commit: 40d8ecae1ac7e0a1df4a2df17f5104bee6ecf336

---


# Configuración de análisis entre dispositivos

> [!NOTE] La documentación de análisis cruzado está sujeta a cambios, ya que la función se desarrolla aún más. Vuelva a comprobar periódicamente las actualizaciones.

Una vez cumplidos todos los requisitos previos, siga los pasos siguientes para habilitar Analytics entre dispositivos. Debe pertenecer a un grupo de Administrador de perfiles de producto o tener privilegios de administrador en Adobe Analytics para seguir estos pasos.

> [!IMPORTANT] Deben cumplirse todos los requisitos previos antes de seguir estos pasos. Si no se cumplen todos los requisitos previos, la función no estará disponible o no funcionará. Consulte [Análisis entre dispositivos](cda-home.md) para conocer los requisitos previos y las limitaciones.

## Elija el grupo de informes entre dispositivos que se habilitará para CDA

Cuando su organización está aprovisionada para utilizar CDA, elige qué grupo de informes utilizar. Esta opción se puede comunicar a través de su Administrador de cuentas de Adobe. A continuación, Adobe habilita el grupo de informes elegido para el procesamiento CDA.

## Crear un grupo de informes virtuales entre dispositivos para ver la vista entre dispositivos

Los administradores con acceso para crear grupos de informes virtuales pueden crear grupos de informes virtuales CDA de la siguiente manera:

1. Vaya a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e inicie sesión con sus credenciales de adobeid.
2. Haga clic en el icono de 9 cuadrícula en la parte superior y, a continuación, haga clic en Analytics.
3. Pase el ratón sobre Componentes en la parte superior y, a continuación, haga clic en Grupos de informes virtuales.
4. Haga clic en Agregar.
5. Introduzca un nombre para el grupo de informes virtuales y asegúrese de que está seleccionado el grupo de informes habilitado para CDA.
6. Haga clic en la casilla'Habilitar procesamiento de tiempo de informe ', que permite varias opciones adicionales, entre ellas, Análisis cruzado de dispositivos.
7. Haga clic en la casilla'Stitch User Visits Across Devices '.
8. Haga clic en Continuar, termine de configurar el grupo de informes virtuales y, a continuación, haga clic en Guardar.

![Casilla CDA](assets/cda-checkbox.png)

## Adiciones y cambios en los grupos de informes virtuales entre dispositivos

Cuando Análisis cruzado esté habilitado en un grupo de informes virtuales, tenga en cuenta los siguientes cambios:

* Aparece un nuevo icono entre dispositivos junto al nombre del grupo de informes virtuales. Este icono es exclusivo de los grupos de informes virtuales entre dispositivos.
* Hay disponibles nuevas métricas con la etiqueta «Personas» y «Dispositivos únicos».
* La métrica «Visitantes únicos» no está disponible, ya que se sustituye por Personas y Dispositivos únicos.
* Al generar segmentos, el contenedor de segmentos'Visitante'se sustituye por un contenedor'Persona '.

## La métrica calculada Compresión calculada

La capacidad de análisis cruzado de dispositivos depende de una amplia gama de factores. La eficacia de la capacidad de la función para unir datos se puede medir con una métrica calculada denominada compresión. Entre los factores que contribuyen a la compresión se incluyen:

* Uso del gráfico de Co-op o del gráfico Privado: En términos generales, las organizaciones que utilizan la cooperación entre dispositivos tienden a ver mejores tasas de compresión que las organizaciones que usan el gráfico privado.
* Tasa de inicio de sesión: Cuanto más usuarios inicien sesión en el sitio, más Adobe podrá identificar y unir visitantes entre dispositivos. Los sitios con una tasa de inicio de sesión baja también tienen tasas de compresión bajas.
* Cobertura de ID de Experience Cloud: Solo se pueden unir los visitantes con un ECID. Un porcentaje más bajo de visitantes que utilizan un ECID correlaciona con tasas de compresión bajas.
* Uso de varios dispositivos: Si los visitantes del sitio no utilizan varios dispositivos, puede ver tasas de compresión bajas.
* Granularidad de informes: La compresión por día suele ser menor que la compresión por mes o año. Las probabilidades de que una persona utilice varios dispositivos se vuelven más pequeñas dentro de un solo día que en un mes entero. Al segmentar, filtrar o utilizar dimensiones de desglose, también se puede mostrar una tasa de compresión inferior.

Para ver la compresión de su organización durante un período de tiempo determinado:

1. Haga clic en Espacio de trabajo en la parte superior y, a continuación, haga clic en'Crear nuevo proyecto '.
2. Comience con un Proyecto en blanco y, a continuación, haga clic en Crear.
3. Arrastre la métrica Dispositivos únicos al área del lienzo rotulada'Borrar una métrica aquí '.
4. Arrastre la métrica Personas al lienzo directamente a la derecha del encabezado de métrica Dispositivos únicos, de manera que las dos métricas están paralelas.
5. Haga clic en el símbolo ' +' junto a las métricas disponibles a la izquierda para abrir el Creador de métricas calculadas.
6. Proporcione esta métrica calculada a la siguiente configuración:
   * Nombre: Compresión entre dispositivos
   * Formato: Porcentaje
   * Cifras decimales: 2
   * Definición: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!NOTE] Haga clic en'Agregar'en la esquina superior derecha del área de definición para agregar un número estático. Arrastre Personas y dispositivos únicos desde la lista de métricas disponibles a la izquierda.
7. Haga clic en Guardar.
8. Arrastre la nueva métrica calculada al lienzo directamente a la derecha del encabezado de métrica Personas, de modo que las tres métricas están paralelas.
9. Opcional: El espacio de trabajo carga la dimensión Día de forma predeterminada. Arrastre una dimensión de fecha alternativa, como semana o mes, en la parte superior de la dimensión Día si desea una granularidad de tiempo diferente.
