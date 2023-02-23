---
description: Envíe un proyecto de Analysis Workspace por correo electrónico o programe su entrega.
keywords: Analysis Workspace
title: Programar proyectos
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
source-git-commit: bf9f04ce6ff057ca66bcf0d9cf66540cea160444
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 88%

---

# Programar proyectos

En el **menú Compartir** de Workspace, puede enviar proyectos de Analysis Workspace por correo electrónico a destinatarios seleccionados. Los archivos se pueden enviar en formato CSV o PDF.

## Enviar archivo ahora

Para enviar un archivo inmediatamente a los destinatarios por correo electrónico:

1. Haga clic en **[!UICONTROL Compartir] > [!UICONTROL Enviar archivo ahora]**.
1. Especifique el tipo de archivo (CSV o PDF).
1. (Opcional) Añada una descripción que se incluirá en el correo electrónico para explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. Haga clic en **[!UICONTROL Enviar ahora]**.
1. (Opcional) Haga clic en **[!UICONTROL Mostrar opciones de programación]** para especificar una programación de entregas.

![Enviar archivo ahora](assets/send-file-now.png)

## Enviar archivo según lo programado

Para enviar un archivo en una programación recurrente a los destinatarios por correo electrónico:

1. Haga clic en **[!UICONTROL Compartir] > [!UICONTROL Enviar archivo según lo programado]**.
1. Especifique el tipo de archivo (CSV o PDF).
1. (Opcional) Añada una descripción que se incluirá en el correo electrónico para explicar el archivo que se va a recibir.
1. Añadir destinatarios o grupos. También se pueden introducir direcciones de correo electrónico.
1. Especifique el rango en el que debe entregarse la programación mediante la modificación de las entradas Inicio en y Finalización en. La fecha de finalización debe ser de un año a partir del día en el que se crea o modifica la programación.
1. Especifique la frecuencia de entrega. Cada frecuencia permite diferentes personalizaciones.
1. Haga clic en **[!UICONTROL Enviar según lo programado]**.

![](assets/send-on-schedule.png)

## Administrador de proyectos programados

Los proyectos programados de Analysis Workspace se pueden administrar en **Analytics > Componentes > Proyectos programados**.

En el Administrador de proyectos programados, puede editar y eliminar la programación recurrente de proyectos. Busque una programación en la barra de búsqueda o utilizando las opciones de filtro en el carril izquierdo. Puede filtrar por etiqueta, programaciones aprobadas, propietarios, etc.

![](assets/scheduled-project-manager2.png)

| Campo | Descripción |
| --- | --- |
| [!UICONTROL Favoritos] | Al seleccionar el icono de estrella, marca esta programación como favorita. |
| [!UICONTROL ID de programación] | Este ID se utiliza principalmente con fines de depuración. |
| [!UICONTROL Título y descripción] | Título y descripción de este proyecto. |
| [!UICONTROL Propietario] | La persona que creó el proyecto y es de su propiedad. |
| [!UICONTROL Etiquetas] | (opcional) El etiquetado es una buena forma de organizar los proyectos. Todos los usuarios pueden crear etiquetas y aplicar una o más a un proyecto. Sin embargo, solo verá las etiquetas de los proyectos que sean suyos o que se hayan compartido con usted. |
| [!UICONTROL Entregado a] | Los destinatarios de este proyecto programado. |
| [!UICONTROL Fecha de caducidad] | La fecha de caducidad predeterminada depende de la frecuencia de programación. Consulte &quot;Fechas de caducidad programadas del proyecto&quot; a continuación. |
| [!UICONTROL Frecuencia] | La frecuencia con la que desea que este proyecto programado se envíe a los destinatarios. |
| [!UICONTROL Hora de ejecución] | A qué hora del día se envía este proyecto programado. |
| [!UICONTROL Cantidad de consultas] | Número de consultas de este proyecto. |

## Acciones comunes

Las siguientes son acciones comunes en el administrador de proyectos programados:

| Acción | Descripción |
|---|---|
| **[!UICONTROL Editar programación]** | Haga clic en el título de la programación para actualizar su configuración de entrega. |
| **[!UICONTROL Eliminar programación]** | Seleccione el proyecto programado en la lista y, a continuación, haga clic en Eliminar en el menú. Esto eliminará la programación seleccionada para el proyecto; el proyecto en sí no se eliminará. |
| **[!UICONTROL Añadir etiquetas]** | Seleccione el proyecto programado en la lista y, a continuación, elija “Etiqueta” o “Aprobar” para organizar las programaciones y facilitar su búsqueda. |
| **[!UICONTROL Ver las programaciones fallidas]** | Vaya al carril izquierdo > Otros filtros > No se han podido ver las programaciones que han fallado. |
| **[!UICONTROL Ver las programaciones caducadas]** | Vaya al carril izquierdo > Otros filtros > Caducado para ver las programaciones que han caducado. Haga clic en el título de la programación para configurar una nueva programación de envío. |
| **[!UICONTROL Ver el ID de programación]** | Vaya a las opciones de columna en la parte superior derecha y añada la columna ID de programación a la tabla. El ID de programación suele ser útil para la depuración. |

El Administrador de programación de proyectos muestra los artículos que ha creado un usuario en particular. Si la cuenta del usuario está desactivada en la aplicación, se detienen todos los envíos programados. La propiedad del proyecto programado se puede **transferir** a un nuevo usuario en **Administración > Usuarios y activos de Analytics > Transferir activos**.

## Fechas de caducidad programadas del proyecto

Las fechas de caducidad de los proyectos programados dependen de la frecuencia de envío programada:

* Los envíos por hora caducan en una semana.
* Los envíos diarios caducan en un mes.
* Las entregas semanales caducan en 6 meses.
* Los envíos mensuales/anuales caducan en un año.
