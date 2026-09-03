---
description: Los archivos de registro ayudan a ver cuándo los usuarios inician la sesión, su uso, los accesos, los grupos de informes y los cambios del administrador.
title: Registros
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
role: Admin
TQID: https://experienceleague.adobe.com/TsWKmf74-b1RhjP0CSGZatLrGN39xDylj9tbFZg5R-Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c6a85389-fb1b-4b26-96ea-08f17fed0c9f
  - id: e44bec7e-8653-4d5b-b53e-60b1ae7c3475
  - id: e499b847-6dc4-408a-9f0b-70d35ce9b711
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 70%

---

# Registros

Los archivos de registro le permiten ver cuándo la gente inicia sesión, su uso, los accesos, los grupos de informes y los cambios de administración.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Registros]**

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
| Error al iniciar sesión | Error del proceso de inicio de sesión del usuario. |
| Inicio de sesión exitoso | El usuario ha iniciado sesión correctamente. |
| Acción del administrador | Se ha producido una acción de administración, como editar un grupo de informes, cambiar la configuración de la empresa, crear un usuario, cancelar una solicitud de creación de informes, etc. |
| Cambio en la configuración de seguridad | Se ha cambiado una configuración de seguridad. |
| Alerta enviada | Se ha enviado una alerta. |
| Acción del usuario | Se ha editado la información del usuario. |
| Herramienta vista | Se ha visto una herramienta. |
| Acción de Omniture | Adobe ha realizado una acción. |
| Recuperación de contraseña | Se ha recuperado una contraseña. |
| Marcadores | Se administró un marcador. |
| Paneles de control | Se ha administrado un tablero. |
| Alertas | Se ha administrado una alerta. |
| Eventos del calendario | Se ha administrado un evento de calendario. |
| Objetivos | Se ha gestionado un destinatario. |
| Configuración de informes | Se administró una configuración del informe. |
| Informes programados | Se ha administrado un informe programado. |
| Excluir por dirección IP | Se ha cambiado la configuración de IP. |
| Asignar nombres a las páginas | Obsoleto. |
| Clasificaciones | Se administró una clasificación. |
| Fuentes de datos | Se administró una fuente de datos. |
| Proyecto de espacio de trabajo | Se ha visto o editado un proyecto de Workspace. |
| Segmento | Se ha creado o editado un segmento. |
| Métrica calculada | Se ha creado o editado una métrica calculada. |
| Intervalo de fechas | Se creó o editó un intervalo de fechas. |
| Grupo de informes virtuales | Se creó o editó un grupo de informes virtuales. |
| Análisis de contribución | Se ha ejecutado un trabajo de análisis de contribución. |
| Método API | Se realizó una llamada de API. |


## Registro de cambios del grupo de informes {#section_3864966639414BBEA871F4D0352F56B6}

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
