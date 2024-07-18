---
description: Consulte y administre informes programados en toda la organización.
title: Administrador de proyectos programados
feature: Admin Tools
exl-id: 8bc8d983-f680-48fa-8483-694c87a9ae4c
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 100%

---

# Proyectos programados

Los proyectos programados de Analysis Workspace se pueden administrar en **Analytics > Componentes > Proyectos programados**.

Al administrar proyectos programados, puede editar y eliminar las programaciones recurrentes de proyectos.

* Cambiar el tipo de archivo (.csv o PDF)
* Actualizar la descripción del proyecto
* Añadir o quitar destinatarios
* Cambiar la frecuencia

Para modificar un proyecto programado

1. Seleccione **Analytics > Componentes > Proyectos programados**.
1. Busque una programación en la barra de búsqueda o utilizando las opciones de filtro en el carril izquierdo. Puede filtrar por [!UICONTROL Etiquetas], [!UICONTROL Propietarios], [!UICONTROL Favoritos] y más.

![Captura de pantalla que muestra la lista de proyectos programados con la columna que muestra el título, el propietario, las etiquetas, entregado a y otras columnas que se describen en la sección Columnas disponibles.](assets/scheduled-project-manager2.png)

## Columnas disponibles

| Campo | Descripción |
| --- | --- |
| [!UICONTROL Favoritos] | Al seleccionar el icono de estrella, marca esta programación como favorita. |
| [!UICONTROL ID de programación] | Este ID se utiliza principalmente con fines de depuración. |
| [!UICONTROL Título y descripción] | Título y descripción de este proyecto. |
| [!UICONTROL Propietario] | La persona que creó el proyecto y es propietaria de él. |
| [!UICONTROL Etiquetas] | (opcional) El etiquetado es una buena forma de organizar los proyectos. Todos los usuarios pueden crear etiquetas y aplicar una o más a un proyecto. Sin embargo, solo verá las etiquetas de los proyectos que sean suyos o que se hayan compartido con usted. |
| [!UICONTROL Entregado a] | Las personas destinatarias de este proyecto programado. |
| [!UICONTROL Fecha de caducidad] | Para cualquier frecuencia de proyecto programado, puede establecer la fecha de caducidad hasta un año en el futuro. |
| [!UICONTROL Frecuencia] | La frecuencia con la que desea que este proyecto programado se envíe a las personas destinatarias. |
| [!UICONTROL Hora de ejecución] | A qué hora del día se envía este proyecto programado. |
| [!UICONTROL Cantidad de consultas] | Número de consultas de este proyecto. |

## Acciones comunes

Las siguientes son acciones comunes en el administrador de proyectos programados:

| Acción | Descripción |
|---|---|
| **[!UICONTROL Editar]** | Seleccione el título de la programación para actualizar la configuración de envío. |
| **[!UICONTROL Eliminar]** | Seleccione el proyecto programado en la lista y, a continuación, haga clic en Eliminar en el menú. Esto eliminará la programación seleccionada para el proyecto; el proyecto en sí no se eliminará. |
| **[!UICONTROL Etiqueta]** | Seleccione el proyecto programado en la lista y, a continuación, elija “Etiqueta” o “Aprobar” para organizar las programaciones y facilitar su búsqueda. |
| **[!UICONTROL Ver las programaciones fallidas]** | Vaya al carril izquierdo > Otros filtros > No se han podido ver las programaciones que han fallado. |
| **[!UICONTROL Ver las programaciones caducadas]** | Vaya al carril izquierdo > Otros filtros > Caducado para ver las programaciones que han caducado. Haga clic en el título de la programación para configurar una nueva programación de envío. |
| **[!UICONTROL Ver el ID de programación]** | Vaya a las opciones de columna en la parte superior derecha y añada la columna ID de programación a la tabla. El ID de programación suele ser útil para la depuración. |

El administrador de proyectos programados muestra los elementos que ha creado una persona concreta. Si la cuenta de usuario está desactivada en la aplicación, se detienen todos los envíos programados. La propiedad del proyecto programado se puede transferir a una nueva persona en **Administración** > **Usuarios y activos de Analytics** > **Transferir activos**.
