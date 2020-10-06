---
description: Instrucciones para configurar los informes de valoración de los paneles.
title: Guía del gestor de datos para paneles de Adobe Analytics
translation-type: tm+mt
source-git-commit: 7ec56bb72638f157b6a501d73495b91ae52d7de9
workflow-type: tm+mt
source-wordcount: '2376'
ht-degree: 94%

---


# Guía del gestor de datos para paneles de Adobe Analytics

La siguiente información enseña a los depuradores de datos de Adobe Analytics sobre cómo configurar y presentar paneles para los usuarios ejecutivos. Para ver un vídeo que muestra esta información, consulte el vídeo del Generador de cuadros de mando de paneles de Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/34544)

## Primeros pasos

Los paneles de Adobe Analytics proporcionan datos de Adobe Analytics en cualquier momento y lugar. La aplicación permite que los usuarios accedan mediante dispositivos móviles a informes de valoración intuitivos que se crean y comparten desde la interfaz de usuario de Adobe Analytics para escritorio. Los informes de valoración son un conjunto de métricas clave y de otros componentes que se presentan en un diseño en mosaico. Los mosaicos se pueden pulsar para obtener desgloses e informes de tendencias más detallados. Puede adaptar los informes de valoración en función de cuáles sean los datos más importantes para usted. Los paneles de Analytics son compatibles con los sistemas operativos iOS y Android.

## Más información sobre esta guía

Esta guía está diseñada para ayudar a los gestores de datos de Adobe Analytics a configurar informes de valoración para sus usuarios ejecutivos en los paneles. Los gestores de datos pueden ser administradores de la organización o personas con otras funciones. Son responsables de la configuración de los informes de valoración de la aplicación, lo que permite a los usuarios ejecutivos ver de forma rápida y sencilla en sus propios dispositivo móviles un amplio conjunto de datos de resumen importantes. Aunque los usuarios ejecutivos son los usuarios finales de los paneles de Analytics, esta guía ayudará a los gestores de datos a configurar la aplicación de forma eficaz para estos usuarios.

## Glosario de términos

En la siguiente tabla se describen los términos para comprender la audiencia, las funciones y el funcionamiento de los paneles de Analytics.

| Término | Definición |
|--- |--- |
| Consumidor | Ejecutivo que ve métricas clave y datos de Analytics en un dispositivo móvil |
| Gestor de datos | Experto que busca y distribuye datos de Analytics y que configura los informes de valoración que verá el consumidor |
| Gestión de datos | Acto de crear o editar un informe de valoración móvil que contenga métricas, dimensiones y otros componentes relevantes para el cliente |
| Informe de valoración | Vista de paneles que contiene uno o más mosaicos |
| Mosaico | Representación de una métrica en una vista del informe de valoración |
| Desglose | Una vista secundaria a la que se puede acceder pulsando un mosaico del informe de valoración. Esta vista ofrece más información sobre la métrica que aparece en el mosaico y, opcionalmente, sobre dimensiones de desglose adicionales |
| Intervalo de fechas | El intervalo de fecha principal para la creación de informes de los paneles |
| Intervalo de fecha de comparación | Intervalo de fecha que se compara con el intervalo de fecha principal |

## Creación de un informe de valoración para los usuarios ejecutivos

Un informe de valoración muestra visualizaciones de datos clave para los usuarios ejecutivos en un diseño en mosaico, tal y como se muestra a continuación:

![Ejemplo de informe de valoración](assets/intro_scorecard.png)

Como gestor, puede utilizar el Generador de informes de valoración para configurar los mosaicos que aparecerán en el informe de valoración de su consumidor. También puede configurar cómo se pueden ajustar las vistas detalladas o los desgloses cuando se pulsen los mosaicos. La interfaz del Generador de informes de valoración se muestra a continuación:

![Generador de informes de valoración](assets/scorecard_builder.png)

Para crear un informe de valoración, deberá hacer lo siguiente:

1. Seleccione la plantilla informe de valoración móvil en blanco.
2. Configure el informe de valoración con datos y guárdelo.

### Selección de la plantilla informe de valoración móvil en blanco

Puede tener acceso a la plantilla informe de valoración móvil en blanco de una de las siguientes formas:

**Creación de un nuevo proyecto**

1. Abra Adobe Analytics y haga clic en la ficha **Espacio de trabajo**.
2. Haga clic en el botón **Crear nuevo proyecto** y seleccione la plantilla de proyecto **informe de valoración móvil en blanco**.
3. Haga clic en el botón **Crear**.

![Plantilla del informe de valoración](assets/new_template.png)

**Agregar un proyecto**

En la pantalla **Proyectos**, en la ficha **Componentes**, haga clic en el botón **Agregar** y seleccione **informe de valoración móvil**.

![Agregar proyectos](assets/add_project.png)

**Uso de las herramientas de Analytics**

En Analytics, haga clic en el menú **Herramientas** y seleccione **Paneles**. En la pantalla siguiente, haga clic en el botón **Crear informe de valoración**.

### Configure el informe de valoración con datos y guárdelo

Para implementar la plantilla del informe de valoración:

1. En **Propiedades** (en el carril derecho), especifique el **grupo de informes de proyecto** cuyos datos quiera utilizar.

   ![Selección del grupo de informes](assets/properties_save.png)

2. Para agregar un nuevo mosaico al informe de valoración, arrastre una métrica desde el panel izquierdo y suéltela en la zona **Arrastrar y soltar métricas aquí**. También puede insertar una métrica entre dos mosaicos del mismo modo.

   ![Agregar mosaicos](assets/build_list.png)


   *Desde cada mosaico puede acceder a una vista detallada que muestra información adicional sobre la métrica, como los elementos principales de una lista de dimensiones relacionadas.*


3. Para agregar una dimensión relacionada a una métrica, arrastre una dimensión desde el panel izquierdo y suéltela en un mosaico. Por ejemplo, puede agregar dimensiones pertinentes (como **Región DMA** en este ejemplo) a la métrica **Visitantes únicos** arrastrándolas y soltándolas en el mosaico; las dimensiones que agregue aparecerán en la sección de desglose de las **Propiedades** específicas del mosaico. Puede agregar varias dimensiones a cada mosaico.

   ![Agregar dimensiones](assets/layer_dimensions.png)

   También puede agregar una dimensión a todos los mosaicos soltándola en el lienzo del informe de valoración.

   Al hacer clic en un mosaico en el Generador de informes de valoración, el carril derecho muestra las propiedades y características asociadas con dicho mosaico. En este carril puede dar un nuevo **Título** al mosaico o, si lo desea, configurarlo especificando componentes en lugar de tener que arrastrarlos y soltarlos desde el carril izquierdo.

   Además, si hace clic en un mosaico, una ventana emergente dinámica le mostrará cómo verá la vista Desglose el usuario ejecutivo de la aplicación. Si no se ha aplicado ninguna dimensión al mosaico, la dimensión de desglose será **hora** o **días**, según el intervalo de fecha predeterminado.

   ![Breakdown_view](assets/break_view.png)

   Cada dimensión agregada al mosaico se mostrará en una lista desplegable de la vista detallada de la aplicación. El usuario ejecutivo puede elegir entre las opciones que se muestran en la lista desplegable.

4. Para aplicar segmentos a mosaicos individuales, arrastre un segmento desde el panel izquierdo y suéltelo directamente sobre el mosaico. Si desea aplicar el segmento a todos los mosaicos del informe de valoración, suelte el mosaico encima del informe de valoración. O bien, también puede aplicar segmentos seleccionando segmentos en el menú de filtro debajo de los intervalos de fechas. Puede [configurar y aplicar filtros para sus informes de valoración](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) del mismo modo que lo haría en Adobe Analytics Workspace.

   ![Generar segmentos para filtrar](assets/segment_ui.png)

5. Del mismo modo, para eliminar un componente que se aplique a todo el informe de valoración, haga clic en cualquier lugar del informe de valoración fuera de los mosaicos y, a continuación, elimínelo haciendo clic en la **x** que aparece al pasar el ratón sobre el componente, como se muestra a continuación para el segmento **Clientes móviles**:

   ![Remove_components](assets/new_remove.png)

6. En **Propiedades** del informe de valoración, también puede especificar de forma opcional lo siguiente:

   * Un **intervalo de fecha predeterminado**. Los intervalos que especifique aquí serán los mismos que se aplicarán cuando el usuario ejecutivo acceda por primera vez al informe de valoración en su aplicación.

   * Un **intervalo de fecha de comparación**

   * Cualquier **segmento** que se aplique a todo el informe de valoración

7. Para asignar un nombre al informe de valoración, haga clic en el área de nombres de la parte superior izquierda de la pantalla y escriba el nuevo nombre.

   ![Naming_Scorecards](assets/new_name.png)

## Uso compartido del informe de valoración

Para compartir el informe de valoración con un usuario ejecutivo:

1. Haga clic en el menú **Compartir** y seleccione **Compartir informe de valoración**.

2. En el formulario **Compartir**, rellene los campos de la siguiente manera:

   * Proporcione el nombre al informe de valoración
   * Proporcione una descripción del informe de valoración
   * Añada las etiquetas relevantes
   * Especificación de los destinatarios del informe de valoración

3. Haga clic en **Compartir**.

![Share_Scorecards](assets/new_share.png)

Una vez que haya compartido un informe de valoración, los destinatarios podrán acceder a él en sus paneles de Analytics. Si realiza cambios posteriores en el informe de valoración mediante el Generador de informes de valoración, estos se aplicarán automáticamente al informe compartido. Los usuarios ejecutivos verán los cambios después de actualizar el informe de valoración en su aplicación.

Si agrega nuevos componentes al informe de valoración, es posible que desee volver a compartirlo (marque la opción **Compartir componentes incrustados**) para asegurarse de que los usuarios ejecutivos tengan acceso a estos cambios.

## Configuración de usuarios ejecutivos con la aplicación

En algunos casos, puede que los usuarios ejecutivos necesiten asistencia adicional para acceder a la aplicación y utilizarla. Esta sección presenta información que le ayudará a proporcionar esa asistencia.

### Ayudar a los usuarios ejecutivos a acceder a la aplicación

Para ayudar a los usuarios ejecutivos a acceder en la aplicación a los informes de valoración que ha creado, asegúrese de que:

* El requisito mínimo del sistema operativo móvil de sus dispositivos sea iOS versión 10 o posterior, o Android versión 4.4 (KitKat) o posterior
* Tengan unas credenciales de inicio de sesión válidas para Adobe Analytics
* Haya creado y compartido correctamente los informes de valoración móviles de los usuarios
* Los usuarios tengan acceso a Analysis Workspace y al grupo de informes en el que se basa el informe de valoración
* Los usuarios tengan acceso a los componentes que se incluyen en el informe de valoración. Tenga en cuenta que, al compartir los informes de valoración, puede seleccionar la opción **Compartir los componentes incrustados**.

### Ayudar a los usuarios ejecutivos de la aplicación

Para ayudar a los usuarios ejecutivos:

1. Ayúdeles a descargar e instalar la aplicación. Siga los siguientes pasos para ampliar el acceso a los usuarios ejecutivos, en función de si utilizan un dispositivo iOS o Android.

   **Para usuarios ejecutivos con iOS:**

   * Haga clic en el siguiente vínculo (también está disponible en Analytics en **Herramientas** > **Paneles**) y siga las indicaciones para descargar, instalar y abrir la aplicación:

      [Vínculo de iOS](https://apple.co/2zXq0aN)
   **Para usuarios ejecutivos con Android:**

   * Haga clic en el siguiente vínculo (también está disponible en Analytics en **Herramientas** > **Paneles**) y siga las indicaciones para descargar, instalar y abrir la aplicación:

      [Vínculo de Android](https://bit.ly/2LM38Oo)
   Una vez descargada e instalada, los usuarios ejecutivos pueden iniciar sesión en la aplicación con sus credenciales de Adobe Analytics; la aplicación es compatible con Adobe ID y con Enterprise/Federated ID.

   ![Pantalla de bienvenida de la aplicación](assets/welcome.png)

2. Ayudar a los usuarios a acceder al informe de valoración que ha creado. Después de que los usuarios ejecutivos inicien sesión en la aplicación, aparecerá la pantalla **Elegir una empresa**. En esta pantalla se muestran las empresas de inicio de sesión a las que pertenece el usuario ejecutivo. Para ayudarles a acceder al informe de valoración:

   * Pulse el nombre de la empresa de inicio de sesión o de la organización de Experience Cloud con la que acceder al informe de valoración que ha compartido. A continuación, la lista de informes de valoración muestra todos los informes de valoración que se han compartido con el usuario ejecutivo y a los que este tiene acceso a través de las credenciales de la empresa.
   * Ayude al usuario ejecutivo a ordenar esta lista por **Últimas modificaciones**, si procede.
   * Pulse el nombre de un informe de valoración para verlo.

   ![Seleccione una empresa](assets/accesscard.png)

   Si el usuario ejecutivo inicia sesión y ve un mensaje que indica que no se ha compartido nada:

   * Es posible que el usuario ejecutivo haya seleccionado una instancia incorrecta de Analytics

   * Es posible que el informe de valoración no se haya compartido con el usuario ejecutivo

      ![No se ha compartido nada](assets/nothing.png)


   * Compruebe que el usuario ejecutivo puede iniciar sesión en la instancia correcta de Analytics y que se ha compartido el informe de valoración.


3. Explain to the executive user how tiles appear in the Scorecards you share (the first Scorecard below is set in dark mode; see **Preferences** below if you think your executive user prefers this viewing opt-on):

   ![Explicación de los mosaicos](assets/newexplain.png)

   ![Ejemplo de informe de valoración](assets/intro_scorecard.png)

   Información adicional sobre los mosaicos:

   * La granularidad de los minigráficos depende de la longitud del intervalo de fecha:
      * Si se selecciona un día se muestra una tendencia horaria
      * Si se selecciona más de un día y menos de un año, se muestra una tendencia diaria
      * Si se selecciona un año o más se muestra una tendencia semanal
   * La fórmula de la variación del valor porcentual es el total de la métrica (intervalo de fecha actual) – el total de la métrica (intervalo de fecha de comparación) / el total de la métrica (intervalo de fecha de comparación).
   * Puede arrastrar la pantalla hacia abajo para actualizar el informe de valoración.


4. Pulse un mosaico para mostrar el funcionamiento de un desglose detallado del mosaico.

   ![Vista de desglose](assets/sparkline.png)

   * Pulse cualquier punto de un minigráfico para ver los datos asociados a ese punto en la línea.

   * Se incluye una tabla para mostrar los datos de las dimensiones agregadas al mosaico. Pulse en la flecha hacia abajo para seleccionar dimensiones. Si no se ha agregado ninguna dimensión al mosaico, la tabla muestra los datos del gráfico.

5. Cambiar los intervalos de fecha del informe de valoración:

   ![Cambio de fechas](assets/changedate.png)

   * También puede cambiar los intervalos de fechas del mismo modo en la vista Desglosar que se muestra arriba.

   * Según el intervalo que pulse (**Día**, **Semana**, **Mes** o **Año**), verá dos opciones para los intervalos de fechas: o el intervalo de tiempo actual o el inmediatamente anterior. Pulse una de estas dos opciones para seleccionar el primer rango. En la lista **COMPARAR CON**, pulse una de las opciones que se muestran para comparar los datos de este periodo de tiempo con el primer intervalo de fecha seleccionado. Pulse **Listo** en la parte superior derecha de la pantalla. El campo **Intervalos de fecha** y los mosaicos del informe de valoración se actualizarán con los nuevos datos de comparación de los nuevos rangos seleccionados.

6. Para dejar comentarios sobre esta aplicación:

   1. Pulse el icono de configuración en la parte superior derecha de la pantalla de la aplicación.
   2. En la pantalla **Configuración**, pulse la opción **Comentarios**.
   3. Pulse para ver las opciones que existen para dejar comentarios.

      ![Pantalla Configuración](assets/settings.png)

7. Para cambiar las preferencias, pulse la opción **Preferencias** que se muestra arriba. En las preferencias, puede activar el inicio de sesión biométrico o puede establecer el modo oscuro de la aplicación, tal y como se muestra a continuación:

   ![Modo oscuro](assets/darkmode.png)

**Para informar de un error**:

Pulse la opción y selecciona la subcategoría del error. En el formulario para informar de un error, escriba su dirección de correo electrónico en el campo superior y una descripción del error en el campo inferior. Al mensaje se adjunta automáticamente una captura de pantalla de la información de su cuenta, pero puede eliminarla si lo desea tocando la **X** de la imagen adjunta. También tiene la opción de grabar la pantalla, agregar más capturas de pantalla o adjuntar archivos. Para enviar el informe, pulse el icono del avión de papel en la parte superior derecha del formulario.


![Informar de un error](assets/newbug.png)

**Para sugerir una mejora**:

Pulse la opción y elija una subcategoría para la sugerencia. En el formulario de sugerencias, escriba su dirección de correo electrónico en el campo superior y una descripción del error en el campo inferior. Al mensaje se adjunta automáticamente una captura de pantalla de la información de su cuenta, pero puede eliminarla si lo desea tocando la **X** de la imagen adjunta. También tiene la opción de grabar la pantalla, agregar más capturas de pantalla o adjuntar archivos. Para enviar la sugerencia, pulse el icono del avión de papel en la parte superior derecha del formulario.

**Para hacer una pregunta**:

Pulse la opción y escriba su dirección de correo electrónico en el campo superior y su pregunta en el campo inferior. Al mensaje se adjunta automáticamente una captura de pantalla, pero puede eliminarla si lo desea tocando la **X** de la imagen adjunta. También tiene la opción de grabar la pantalla, agregar más capturas de pantalla o adjuntar archivos. Para enviar la pregunta, pulse el icono del avión de papel en la parte superior derecha del formulario.

>[!IMPORTANT]
>
>A partir de octubre de 2020, Adobe está implementando gradualmente una serie de mejoras para optimizar el rendimiento de la aplicación &quot;Adobe Analytics paneles&quot;. Estas mejoras se centran en el almacenamiento en caché de datos históricos de Analytics que se utilizan para rellenar cuadros de mandos con fechas (excluido el día actual). Estos datos se almacenarán en caché durante un máximo de 24 horas en una cuenta segura de almacenamiento público en la nube de Microsoft Azure. Comuníquese con el CSM si desea exclusión estas funciones de mejora de rendimiento.
