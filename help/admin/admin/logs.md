---
description: Los archivos de registro ayudan a ver cuándo los usuarios inician la sesión, su uso, los accesos, los grupos de informes y los cambios del administrador.
title: Registros
topic: Admin tools
uuid: d5d4723d-f4cf-403e-ae9c-76d7faed2be6
translation-type: tm+mt
source-git-commit: 3603722ee3cbaf64b6d7bc0cbfa4af176f85a87a
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 97%

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
| Report Suite | Filtre el registro por un ID de grupo de informes específico. |
| Tipo de evento | Filtre el registro por tipo de evento. Seleccione un tipo de evento de la lista desplegable. Consulte la lista completa de tipos de evento a continuación. |
| Evento | Filtre el registro por una palabra o frase de la descripción del evento. |
| Descargar informe | Exporta el contenido del [!UICONTROL registro de uso y acceso] a un archivo delimitado por tabulaciones. |

### Tipos de eventos

| Tipo de evento | Descripción |
| --- |--- |
| Ninguna categoría |  |
| Falló el inicio de sesión |  |
| Inicio de sesión exitoso |  |
| Acción del administrador |  |
| Cambio en la configuración de seguridad |  |
| Informe visto |  |
| Informe descargado |  |
| Alerta enviada |  |
| Acción del usuario |  |
| Herramienta vista |  |
| Acción de Omniture |  |
| Recuperación de contraseña |  |
| Marcadores |  |
| Tableros |  |
| Alertas |  |
| Eventos de calendario |  |
| Objetivos |  |
| Configuración de informes |  |
| Informes programados |  |
| Excluir por dirección IP |  |
| Nombrar páginas |  |
| Clasificaciones |  |
| Fuentes de datos |  |
| Proyecto de espacio de trabajo |  |
| Segmento |  |
| Métrica calculada |  |
| Intervalo de fechas |  |
| Grupo de informes virtuales |  |
| Análisis de contribución |  |
| Solicitud de bloque de datos de Excel |  |
| Error en el inicio de sesión de Excel |  |
| Inicio de sesión exitoso en Excel |  |
| Error en el inicio de sesión de Mobile |  |
| Inicio de sesión exitoso en Mobile |  |
| Método API |  |


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

