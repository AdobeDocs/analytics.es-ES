---
description: Las listas de publicaciones facilitan el envío de diversos informes específicos a distintos grupos de la organización sin necesidad de crear varios informes programados independientes. Las listas de publicaciones resultan útiles si se dispone de grupos de informes que son específicos de una ubicación y se desea proporcionar a cada respectivo departamento una copia de un tablero concreto. Estas listas también se pueden usar para enviar datos a muchas personas sin necesidad de introducir una por una las direcciones de correo electrónico, en caso de trabajar con un único grupo de informes.
title: Listas de publicaciones
feature: Admin Tools
uuid: 07dad661-c302-4981-80d1-3169ad1fe90e
exl-id: 5c9a0ae7-742b-4247-bcbc-2e979af6160c
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 52%

---

# Listas de publicaciones

Las listas de publicaciones facilitan el envío de diversos informes específicos a distintos grupos de la organización sin necesidad de crear varios informes programados independientes. Las listas de publicaciones resultan útiles si se dispone de grupos de informes que son específicos de una ubicación y se desea proporcionar a cada respectivo departamento una copia de un tablero concreto. Estas listas también se pueden usar para enviar datos a muchas personas sin necesidad de introducir una por una las direcciones de correo electrónico, en caso de trabajar con un único grupo de informes.

Al programar un informe, se pueden especificar varias listas de publicaciones.

## Fin de vida útil de las listas de publicaciones

Como probablemente sepa, el Adobe eliminará de Reports and Analytics (R&amp;A) y el producto específico de Site Catalyst el 31 de diciembre de 2023. [Puede obtener más información sobre el final de su vida útil y cómo puede prepararse para ello aquí](https://express.adobe.com/page/6WnF8JK6IRDhf/).

Una de las funciones de I+A que está previsto que llegue al final de su vida útil en esta fecha es Listas de publicaciones. Algunas funciones, como Eventos de calendario y Informe de resumen de página , tienen o tendrán una versión de paridad en Analysis Workspace. Sin embargo, las Listas de publicaciones no son una de ellas y quedarán obsoletas cuando la I+A llegue a su fin de vida útil. **No podrá crear Listas de publicación nuevas ni acceder a las existentes para enviar o programar proyectos de Analysis Workspace.**

Para mitigar cualquier interrupción de los flujos de trabajo de distribución de informes actuales que dependen de listas de publicaciones, le solicitamos que considere las siguientes alternativas:

* Si utiliza Listas de publicaciones para distribuir la misma versión del informe a varios usuarios (sin aplicar anulaciones de grupos de informes):

   Una vez que vuelva a crear los informes en Analysis Workspace como proyectos, puede utilizar una combinación de un grupo de contacto o una lista de distribución creada para su cliente de correo y la función Proyectos programados de Workspace para enviar o programar la entrega recurrente del proyecto. Al igual que las listas de publicaciones, se envía una versión de PDF/CSV del proyecto a cada ID de correo electrónico que forme parte del grupo o lista. Puede obtener más información sobre [Proyectos programados aquí](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html#:~:text=Scheduled%20Analysis%20Workspace%20projects%20can,options%20in%20the%20left%20rail.).

* Si utiliza Listas de publicaciones para distribuir varias versiones del informe o del tablero a varios usuarios (mediante la función de anulación del grupo de informes):

   Analysis Workspace no admite la anulación de grupos de informes. Tampoco admite la capacidad de bloquear grupos de informes al compartir o programar proyectos. Para replicar el flujo de trabajo, es posible que tenga que crear varias versiones del mismo proyecto con un grupo de informes diferente aplicado a cada versión y, a continuación, utilizar la función de proyecto programado descrita anteriormente.

Para obtener más información o ayuda, póngase en contacto con el Servicio de atención al cliente de Adobe.

## Descripciones del Administrador de la Lista de publicaciones {#section_099DF8AC5691495F9B22C71266DD6004}

| Elemento | Descripción |
|--- |--- |
| [!UICONTROL Buscar] | Permite filtrar la tabla para buscar una lista de publicaciones. |
| [!UICONTROL Grupos de informes que desea incluir] | Anula el grupo de informes de un informe programado o todos los informes breves de un tablero. Aunque técnicamente no existe ningún límite en cuanto al número de entradas de grupo de informes independientes, se recomienda no superar las 50 aproximadamente. No hay ningún límite establecido en cuanto al número de correos electrónicos que se pueden incluir. |
| [!UICONTROL Direcciones de correo electrónico] | Lista delimitada por comas de todas las direcciones de correo electrónico que recibirán el informe con el grupo de informes nuevo.  Haga clic en **[!UICONTROL Haga clic para editar]** para especificar las direcciones de correo electrónico de los destinatarios. Escriba las direcciones de correo electrónico separadas por punto y coma (;). Pulse `<Enter>` cuando haya terminado de escribir las direcciones de correo electrónico. <br>El campo Número de direcciones indica la cantidad de direcciones de correo electrónico que están asociadas a la entrada del grupo de informes. |
| [!UICONTROL Duplicar] | Crea una copia de la lista de publicaciones. |
