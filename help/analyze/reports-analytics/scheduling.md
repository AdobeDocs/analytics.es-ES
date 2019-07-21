---
description: Información sobre cómo programar, descargar y distribuir informes.
seo-description: Información sobre cómo programar, descargar y distribuir informes.
seo-title: Programación y distribución de informes
solution: Analytics
subtopic: Programa
title: Programación y distribución de informes
topic: Reports and Analytics
uuid: 1230 b 0 f 3-e 026-4 b 83-b 231-14 d 6 f 75 a 3836
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Programación y distribución de informes

Información sobre cómo programar, descargar y distribuir informes.

## Report schedule and distribution {#concept_4EA333DFC7FD4E9CA086385A3DA10BE9}

Información sobre cómo programar, descargar y distribuir informes.

Al programar un informe para su envío a una aplicación de Adobe Analytics, se pueden utilizar las herramientas de programación y distribución para ver qué archivos se han enviado automáticamente y así modificar o finalizar los envíos.

Debido a las diferencias en los mecanismos y las plataformas de procesamiento, los varios tipos de informes descargables y programados disponibles en Adobe Analytics tienen diferentes limitaciones con relación al número máximo de filas que pueden procesar en una única solicitud. Estos son los límites de cada uno:

* Word, CSV, Excel, HTML y PDF: el mismo número de filas visibles en el informe. De forma predeterminada, este límite es 50 filas, pero se puede aumentar hasta 200. Los informes de desglose tienen un límite estricto de 50 filas.
* Data Extract: 50 000 filas
* Data Warehouse: sin límite

Tenga en cuenta que estas limitaciones son para los informes individuales programados y descargados; los tableros se limitan a la cantidad de espacio disponible en un informe breve.

## Enviar un informe {#task_27642CD33D484FD0BF59EBD159EEF52C}

Instrucciones sobre cómo descargar y enviar por correo electrónico informes en diversos formatos, y sobre cómo programar un informe para su envío.

<!-- 

t_send_report.xml

 -->

1. Run a report, then click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.
1. Especifique las opciones de envío:

   | Opción | Descripción |
   |--- |--- |
   | Formato | Seleccione PDF o HTML. |
   | Enviar a | Suministrar una dirección de correo electrónico para recibir el informe. |
   | Asunto | Asunto del correo electrónico. |
   | Programación | Seleccionar para enviar el informe inmediatamente o con un intervalo distinto. |

1. Click **[!UICONTROL Advanced Delivery Options]** to specify a delivery schedule.

   <table id="choicetable_2934E54FEE6E4D33B07EAC21F6DF628E"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Opción </th> 
   <th class="chdeschd"> Descripción </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Nombre del archivo del informe</strong></td> 
   <td class="chdesc stentry"> <p>Especifica el nombre del informe. El formato predeterminado es <code>&lt;nombre del informe&gt; para &lt;grupo&gt; - &lt;intervalo de fechas del informe&gt; </code>. </p> <p>Para especificar un nombre personalizado, seleccione <span class="uicontrol">Personalizar </span>. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Formato del informe</strong></td> 
   <td class="chdesc stentry"> <p>Le permite especificar formatos PDF, CSV, Excel, HTML, Word o Móvil para el envío. Si selecciona CSV, también puede especificar la codificación para CSV: </p> <p> 
      <ul id="ul_4A2EB8D9512246589994052CF482BFD7"> 
      <li id="li_A4FC4D795A9D4F92AAB187ACDFBA180D"> <p> <span class="uicontrol"> Shift-JIS</span>: codificación de caracteres japoneses. </p> </li> 
      <li id="li_405C7EC97F994D649A50F84466FADA3D"> <p> <span class="uicontrol"> EUC-JP</span>: código Unix ampliado, principalmente para japonés, coreano y chino simplificado. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Contenido del informe</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Número de filas de la tabla</span>: especifica el número de filas que desea que sean visibles en la tabla del informe que está enviando. </p> <p> <span class="uicontrol"> Idioma para el encabezado y pie de página</span>: especifica el idioma del encabezado y el pie de página. </p> <p> <span class="uicontrol"> Comentarios</span>: especifica el texto que aparece al comienzo del informe. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Enviar el archivo de firma digital</strong></td> 
   <td class="chdesc stentry"> <p>Si solicita un informe como, por ejemplo, un informe con marcadores o solicitudes de Data Warehouse, puede solicitar una firma de los datos. La firma digital de Adobe no restringe el acceso a la información, pero el propósito del archivo de firma digital (.sig) es verificar la validez del archivo de informes enviado. Si utiliza la firma digital, los destinatarios del informe pueden verificar si el archivo proviene de Adobe y si no ha sido alterado. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Destino del informe</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Correo electrónico</span>: permite configurar las direcciones de correo electrónico, la línea de asunto y las notas. </p> <p> <span class="uicontrol"> FTP</span>: permite configurar FTP, incluso el host, el puerto, el directorio, el nombre de usuario y la contraseña. </p> </td> 
   </tr> 
   </table>

1. Click **[!UICONTROL Scheduling Options]**.

   <table id="choicetable_589A39087F4C497D8913364FFF0125B7"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Opción </th> 
   <th class="chdeschd"> Descripción </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Enviar informe ahora</strong></td> 
   <td class="chdesc stentry"> <p>Envía el informe inmediatamente. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Programar después</strong></td> 
   <td class="chdesc stentry"> <p>Muestra las opciones para especificar un intervalo de tiempo y las opciones de envío. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Intervalo de tiempo del informe</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Fijo</span>: evita que la fecha avance con el transcurso del tiempo. </p> <p> <span class="uicontrol"> Móvil</span>: permite que la fecha avance con el transcurso del tiempo. Algunas consideraciones: </p> <p> 
      <ul id="ul_5CDCCBEFEB364800A428614183A0E6A1"> 
      <li id="li_37B8F32A9E3B4979B5239A58F0C5A71C"> <p>Si selecciona móvil tanto para la fecha de inicio como para la de finalización y selecciona un informe diario del día anterior, recibirá un mensaje de correo electrónico todos los días con el informe del día anterior. </p> </li> 
      <li id="li_83FFD2400C6A453783CDD9BB3B9BA3F9"> <p>Si selecciona fijo para la fecha de inicio y móvil para la fecha de finalización, recibirá el primer día un informe del día anterior. El segundo día recibirá un informe de los dos días anteriores, el tercer día recibirá un informe de los tres días anteriores y así sucesivamente. </p> </li> 
      <li id="li_28F8552D699841BC942058247D39DBB9"> <p>Si selecciona fijo tanto para la fecha de inicio como para la de finalización, recibirá un informe idéntico para los días precisos que haya especificado. </p> </li> 
      <li id="li_A594A6E2A4044ED6AC0A80F88EB203B3"> <p>No es posible seleccionar una fecha de inicio móvil y una de finalización fija. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Frecuencia de envío</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Por hora</span>: envía un mensaje de correo electrónico cada hora, cada dos horas o a cualquier otro intervalo de horas. </p> <p> <span class="uicontrol"> Diario</span>: envía un mensaje de correo electrónico todos los días, cada dos días, cada tres días o a cualquier otro intervalo de días. También es posible que se envíe cada día laborable. </p> <p> <span class="uicontrol"> Semanal</span>: envía un mensaje de correo electrónico todas las semanas, cada dos semanas, cada tres semanas o a cualquier otro intervalo de semanas. También se puede especificar qué día de la semana enviarlo. </p> <p> <span class="uicontrol"> Mensualmente</span>: especifica el intervalo en cantidad de meses y se puede también seleccionar el día del mes en que ha de enviarse o el día de una determinada semana del mes. </p> <p> <span class="uicontrol"> Anualmente</span>: especifica el día del año en que ha de enviarse el informe o bien puede enviarse un día de la semana de cualquier semana del año. </p> <p> <span class="uicontrol"> Hora del día</span>: se aplica al huso horario conectado al grupo de informes seleccionado. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Opciones de finalización de envío</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Sin fin</span>: especifica sin fin. </p> <p> <span class="uicontrol"> Finalizar después de &lt;valor&gt; ocurrencias</span>: especifica el número de ocurrencias antes de finalizar el envío. </p> <p> <span class="uicontrol"> Finalizar el</span>: permite especificar una fecha determinada. </p> <p>Si desea que los datos se procesen en la misma fecha que los datos del informe, el informe contendrá solamente los datos que se hayan incluido en la base de datos en el momento en el que se envíe el informe. Puesto que el procesamiento completo de un día puede llevar hasta 24 horas, es posible que no estén disponibles los datos completos al tiempo de enviar el informe. Para obtener los datos completos, siempre fije el tiempo de procesamiento en 24 horas después del final del período de informe. </p> </td> 
   </tr> 
   </table>

## Imprimir un informe {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Instrucciones sobre cómo imprimir un informe.

<!-- 

t_reports_print.xml

 -->

1. Ejecutar un informe.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Print]**.  ![](assets/print.png)

## Descarga de un informe usando opciones avanzadas {#task_43660107A1C9485D92981CD75B562577}

Descargue información detallada sobre un informe concreto en los formatos PDF, CSV, Excel o Raw Data Export.

<!-- 

t_download-report.xml

 -->

1. En **Analytics** &gt; **[!UICONTROL Informes]**, seleccione un informe para verlo.
1. Haga clic en **[!UICONTROL Descargar]**.

   ![](assets/download_basic.png)

1. Seleccione el formato que desee para el informe:

   * **[!UICONTROL PDF]**: especifica que el informe se descargará en formato de Adobe PDF, lo cual le permite compartir el informe con otros usuarios que podrán abrirlo sin importar el sistema informático que estén utilizando. 
   * **[!UICONTROL CSV]**: Especifica que el informe se descargará en [!DNL .csv] (formato de valores separados por comas).
   * **[!UICONTROL Excel]**: especifica que el informe se descargará en formato de Microsoft Excel, lo cual le permite compartir el informe con otros usuarios que podrán abrirlo en un programa de hojas de cálculo.
   * **[!UICONTROL Word]**: especifica que el informe se descargará en formato Microsoft Word.
   >[!NOTE]
   >
   >Si utiliza uno de los formatos de exportación sin procesar para descargar un informe y el nombre de la página está en blanco, es probable que Adobe Analytics no haya tenido tiempo suficiente para procesar los datos. Descargue el informe más tarde.

## Administrar informes programados {#task_C17677C543454FF2B06D10EA5652DFBC}

Información sobre cómo administrar los informes programados.

<!-- 

t_schedule_manage.xml

 -->

En el [!UICONTROL Administrador de programación de informes], puede editar y eliminar los envíos periódicos de informes. Puede crear programas de entregas que envíen los informes por correo electrónico o por FTP a una dirección especificada. Puede configurar los programas a fin de que los informes se envíen automáticamente a intervalos especificados por un periodo de tiempo o indefinidamente, o bien para que se detenga el envío de un informe recurrente.

El [!UICONTROL Administrador de programación de informes] muestra los artículos que ha creado un usuario en particular. Si la cuenta del usuario está desactivada en la aplicación, se detienen todos los envíos programados.

1. To access the manager, click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**.

## Compartir un vínculo a un informe {#task_9711DDE9E140451B8C914EC5513E21EC}

Instrucciones sobre cómo compartir un informe generando un vínculo de informe (una dirección URL) para enviarlo a otro usuario.

<!-- 

t_reports_share_link.xml

 -->

Cuando el destinatario hace clic en el vínculo, el sistema solicita las credenciales de inicio de sesión (nombre de la empresa, nombre de usuario y contraseña). Después de iniciar sesión, el destinatario se muestra en el informe generado por el usuario original. Se aplican restricciones de permiso estándar.

**Para compartir un vínculo del informe**

1. Ejecutar un informe.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Link to This Report]**.

## Cancelación de la suscripción de informes programados {#concept_6B48360F935740B6851BA85D32DEF637}

Puede cancelar la suscripción de informes programados. Dejará de recibir el informe aunque se vuelva a agregar su nombre de usuario en el informe programado.

<!-- 

t_schedule_unsubscribe.xml

 -->

>[!IMPORTANT]
>
>Para que pueda recibir nuevamente el informe, es necesario crear una nueva programación.

Para cancelar una suscripción de un informe programado:

1. Acceda el correo electrónico con el vínculo al informe cuya suscripción desea cancelar.

   ![](assets/unsubscribe-email.png)

1. Haga en el vínculo **[!UICONTROL haga clic aquí]** junto a **[!UICONTROL Para cancelar el envío automático de este informe]**.

1. Confirme que desea cancelar el envío del informe.

   >[!NOTE]
   >
   >Este flujo de trabajo es el mismo tanto si usted es el programador de informes como si es el destinatario del informe.

Al cancelar la suscripción de un informe no se cancela el informe programado.

Para cancelar un informe programado, vaya al Administrador de programación y haga clic en la X roja junto al nombre de informe. [Más...](../../analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
