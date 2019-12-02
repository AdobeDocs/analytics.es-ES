---
title: Configuración de análisis entre dispositivos
description: Obtenga información sobre cómo configurar Analytics entre dispositivos después de cumplir los requisitos previos.
translation-type: ht
source-git-commit: 8c5e8d18ce4e09049d3fea07b8dd75ded6894313

---


# Configuración de análisis entre dispositivos

> [!NOTE] La documentación de Análisis entre dispositivos está sujeta a cambios a medida que la función se desarrolla. Vuelva regularmente para ver las actualizaciones.

Una vez cumplidos todos los requisitos previos, siga los pasos siguientes para habilitar el análisis entre dispositivos. Debe pertenecer a un grupo de administradores de perfil de producto o tener privilegios de administrador en Adobe Analytics para seguir estos pasos.

> [!IMPORTANT] Todos los requisitos previos deben cumplirse antes de seguir estos pasos. Si no se cumplen todos los requisitos previos, la función no estará disponible o no funcionará. Consulte [Análisis entre dispositivos](cda-home.md) para conocer los requisitos previos y las limitaciones.

## Elija el grupo de informes entre dispositivos que se habilitará para CDA

Cuando su organización está aprovisionada para utilizar CDA, usted elige qué grupo de informes utilizar. Esta opción se puede comunicar a través del administrador de cuentas de Adobe. A continuación, Adobe habilita el grupo de informes elegido para el procesamiento de CDA.

## Crear un grupo de informes virtuales entre dispositivos para ver la vista entre dispositivos

Los administradores con acceso para crear grupos de informes virtuales pueden crear grupos de informes virtuales CDA de la siguiente manera:

1. Vaya a [experience.adobe.com](https://experiencecloud.adobe.com) e inicie sesión con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrículas en la parte superior y, a continuación, haga clic en Analytics.
3. Pase el ratón sobre los componentes en la parte superior y, a continuación, haga clic en Grupos de informes virtuales.
4. Haga clic en Agregar.
5. Escriba un nombre para el grupo de informes virtuales y asegúrese de que está seleccionado el grupo de informes habilitado para CDA.
6. (Opcional) Aplique un segmento al grupo de informes virtuales. Por ejemplo, puede aplicar un segmento que limite el grupo de informes virtuales a las fechas después de activar CDA y de iniciar la vinculación. Este segmento permite a los usuarios ver solamente intervalos de fechas enlazados dentro del VRS.
7. Haga clic en la casilla de verificación “Habilitar procesamiento de tiempo de informes”, que permite varias opciones más, incluido Análisis entre dispositivos.
8. Haga clic en la casilla de verificación “Estirar las visitas del usuario entre dispositivos”.
9. Haga clic en Continuar, termine de configurar el grupo de informes virtuales y, a continuación, haga clic en Guardar.

![Casilla CDA](assets/cda-checkbox.png)

## Adiciones y cambios en los grupos de informes virtuales entre dispositivos

Cuando Análisis entre dispositivos está habilitado en un grupo de informes virtuales, tenga en cuenta los siguientes cambios:

* Aparece un nuevo icono entre dispositivos junto al nombre del grupo de informes virtuales. Este icono es exclusivo para grupos de informes virtuales entre dispositivos.
* Hay disponibles nuevas métricas etiquetadas como “Personas” y “Dispositivos únicos”.
* La métrica “Visitantes únicos” no está disponible, ya que se sustituye por Personas y Dispositivos únicos.
* Al generar segmentos, el contenedor de segmentos “Visitante” se reemplaza por un contenedor “Persona”.

## La métrica calculada Compresión

La capacidad de los análisis entre dispositivos para unir dispositivos depende de una amplia variedad de factores. La eficacia de la capacidad de la función para unir datos se puede medir con una métrica calculada llamada compresión. Los factores que contribuyen a la compresión incluyen:

* Uso del gráfico de colaboración o del gráfico privado: En términos generales, las organizaciones que utilizan la colaboración entre dispositivos tienden a ver mejores tasas de compresión que las organizaciones que utilizan el gráfico privado.
* Velocidad de inicio de sesión: Cuantos más usuarios inicien sesión en el sitio, más podrá Adobe identificar y unir a los visitantes entre dispositivos. Los sitios con una tasa de inicio de sesión baja también tienen tasas de compresión bajas.
* Cobertura del Experience Cloud ID: Solo se pueden vincular los visitantes con un ECID. Un porcentaje menor de visitantes que utilizan un ECID se correlaciona con tasas de compresión más bajas.
* Uso de varios dispositivos: Si los visitantes del sitio no utilizan varios dispositivos, puede ver tasas de compresión más bajas.
* Granularidad de informes: La compresión por día suele ser menor que la compresión por mes o año. Las posibilidades de que un individuo utilice varios dispositivos se reducen en un solo día en comparación con todo un mes. Segmentar, filtrar o utilizar dimensiones de desglose también puede mostrar una tasa de compresión más baja.

Para ver la compresión de su organización durante un período de tiempo determinado:

1. Haga clic en Workspace en la parte superior y, a continuación, en “Crear nuevo proyecto”.
2. Comience con un proyecto en blanco y, a continuación, haga clic en Crear.
3. Arrastre la métrica Dispositivos únicos al área del lienzo rotulada “Colocar una métrica aquí”.
4. Arrastre la métrica Personas al lienzo directamente a la derecha del encabezado de métrica Dispositivos únicos, de modo que las dos métricas estén una al lado de la otra.
5. Haga clic en el símbolo “`+`” al lado de las métricas disponibles a la izquierda para abrir el Creador de métricas calculadas.
6. Asigne esta métrica calculada a la siguiente configuración:
   * Nombre: Compresión entre dispositivos
   * Formato: Porcentaje
   * Cifras decimales: 2
   * Definición: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Haga clic en “Agregar” en la esquina superior derecha del área de definición para agregar un número estático. Arrastre Personas y Dispositivos únicos desde la lista de métricas disponibles a la izquierda.
7. Haga clic en Guardar.
8. Arrastre la nueva métrica calculada al lienzo directamente a la derecha del encabezado de la métrica Personas, de modo que las tres métricas estén una al lado de la otra.
9. Opcional: El espacio de trabajo carga la dimensión Día de forma predeterminada. Arrastre una dimensión de fecha alternativa, como semana o mes, sobre la dimensión Día si desea una granularidad de tiempo diferente.
