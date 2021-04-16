---
description: Los archivos de registro ayudan a ver cuándo los usuarios inician la sesión, su uso, los accesos, los grupos de informes y los cambios del administrador.
title: Registros
feature: Herramientas de administración
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 72%

---

# Registros

Los archivos de registro ayudan a ver cuándo los usuarios inician la sesión, su uso, los accesos, los grupos de informes y los cambios del administrador.

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Registros]**

## Registro de administración {#section_8ADE8A7204A8401C968ABC20AECA381D}

El registro de administración crea informes de todos los cambios realizados por los administradores en las Herramientas de administración. El registro es la forma de acceder a los informes definidos por el usuario desde cualquiera de los tres registros. Puede buscar los eventos que coincidan con sus criterios de selección en el rango de fechas especificado.

## Registro de uso y acceso {#section_6FBAF92D9EA244809C45A78A2F0A7232}

El [!UICONTROL registro de uso y acceso] permite evaluar el uso de los informes en el nivel de cuentas de usuario. Por ejemplo, permite efectuar un seguimiento de las acciones de apertura, creación, actualización, interrupción del uso compartido y eliminación en Analysis Workspace. Esto ofrece una mejor visibilidad sobre los usuarios que usan Workspace y la frecuencia con la que lo hacen.

| Elemento | Descripción |
|---|---|
| Intervalo de fechas | Especifique un filtro de intervalo de fechas. Puede introducir una fecha manualmente, con el formato AAAA-MM-DD, o hacer clic en el icono del calendario para seleccionar una fecha. |
| Inicio de sesión | Filtre el registro por nombre de usuario. |
| IP | Filtre el registro por dirección IP. |
| Grupo de informes | Filtre el registro por un ID de grupo de informes específico. |
| Tipo de evento | Filtre el registro por tipo de evento. Seleccione un tipo de evento de la lista desplegable. Consulte la lista completa de tipos de eventos a continuación. |
| Evento | Filtre el registro por una palabra o frase de la descripción del evento. |
| Descargar informe | Exporta el contenido del [!UICONTROL registro de uso y acceso] a un archivo delimitado por tabulaciones. |

### Tipos de eventos

| Tipo de evento | Descripción |
| --- | --- |
| Ninguna categoría | Puede ser cualquier tipo de evento. |
| Falló el inicio de sesión | Error en el proceso de inicio de sesión del usuario. |
| Inicio de sesión exitoso | El usuario ha iniciado sesión correctamente. |
| Acción del administrador | Se ha producido una acción de administrador, como editar un grupo de informes, cambiar la configuración de la empresa, crear un usuario, etc. |
| Cambio en la configuración de seguridad | Se ha cambiado una configuración de seguridad. |
| Informe visto | Se visualizó un informe de Reports &amp; Analytics. |
| Informe descargado | Se descargó un informe de Reports &amp; Analytics. |
| Alerta enviada | Se envió una alerta. |
| Acción del usuario | Se editó la información del usuario. |
| Herramienta vista | Se ha visto una herramienta. |
| Acción de Omniture | Adobe realizó una acción. |
| Recuperación de contraseña | Se recuperó una contraseña. |
| Marcadores | Se administró un marcador. |
| Tableros | Se administró un tablero. |
| Alertas | Se administró una alerta. |
| Eventos de calendario | Se administró un evento de calendario. |
| Objetivos | Se administró un objetivo. |
| Configuración de informes | Se administró una configuración de informe. |
| Informes programados | Se administró un informe programado. |
| Excluir por dirección IP | Se ha cambiado la configuración de la IP. |
| Nombrar páginas | Obsoleto. |
| Clasificaciones | Se administró una clasificación. |
| Fuentes de datos | Se administró una fuente de datos. |
| Proyecto de espacio de trabajo | Se ha visualizado o editado un proyecto de Workspace. |
| Segmento | Se creó o editó un segmento. |
| Métrica calculada | Se creó o editó una métrica calculada. |
| Intervalo de fechas | Se creó o editó un intervalo de fechas. |
| Grupo de informes virtuales | Se creó o editó un grupo de informes virtuales. |
| Análisis de contribución | Se ejecutó un trabajo de análisis de contribución. |
| Método API | Se realizó una llamada de API. |


## Registro de cambios del grupo de informes  {#section_3864966639414BBEA871F4D0352F56B6}

El registro de cambios del grupo de informes muestra los cambios realizados en los grupos de informes fuera de la administración.

Las herramientas que pueden modificar un grupo de informes desde fuera de las [!UICONTROL Herramientas de administración] son las siguientes:

* Cargas de clasificaciones realizadas en un explorador web (las cargas de clasificaciones realizadas mediante FTP no están incluidas en el registro de cambios)
* Cambios realizados en versiones anteriores.
* Cambios realizados por un representante de cuentas o por el Servicio de atención al cliente con herramientas internas

| Elemento | Descripción |
|---|---|
| Intervalo de fechas | Especifique un filtro de intervalo de fechas. Puede introducir una fecha manualmente, con el formato AAAA-MM-DD, o hacer clic en el icono del calendario para seleccionar una fecha. |
| Empresa | Filtre el registro por nombre de empresa. |
| Inicio de sesión | Filtre el registro por nombre de usuario. |
| IP | Filtre el registro por dirección IP. |
| Evento | Filtre el registro por una palabra o frase de la descripción del evento. |
| Descargar informe | Exporta el contenido del [!UICONTROL registro de uso y acceso] a un archivo delimitado por tabulaciones. |
