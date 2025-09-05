---
description: Antes de empezar a crear grupos de informes virtuales, hay que tener algunos aspectos en cuenta.
keywords: Grupo de informes virtuales
title: Crear un grupo de informes virtuales
feature: VRS
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 62%

---

# Crear un grupo de informes virtuales

Antes de empezar a crear grupos de informes virtuales, hay que tener algunos aspectos en cuenta.

* Los usuarios no administradores no pueden ver el Administrador de grupos de informes virtuales.
* Los grupos de informes virtuales no se pueden compartir. El uso compartido se realiza mediante grupos/permisos.
* En el administrador de grupos de informes virtuales solo puede ver sus propios grupos. Debe hacer clic en “Mostrar todos” para ver los de otros usuarios.

1. Vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Grupos de informes virtuales]**.
1. Haga clic en **[!UICONTROL Agregar +]**.

   ![](assets/new_vrs.png)

## Definir la configuración

En la pestaña [!UICONTROL Configuración], defina esta configuración y haga clic en **[!UICONTROL Continuar]**.

| Elemento | Descripción |
| --- |--- |
| Nombre | El nombre del grupo de informes virtuales no se hereda del grupo de informes superior y debe ser distinto. |
| Descripción | Agregue una buena descripción para los usuarios empresariales. |
| Etiquetas | Puede agregar etiquetas para organizar los grupos de informes. |
| Fuente | El grupo de informes del que surge este grupo de informes virtuales hereda la siguiente configuración. La mayoría de los niveles y funciones de servicio (por ejemplo, la configuración eVar, las reglas de procesamiento, las Clasificaciones, etc.) se heredan. Para realizar cambios en esta configuración heredada en un grupo de informes virtuales, debe editar el grupo de informes superior (Administración > Grupos de informes). |
| Zona horaria | Elegir una zona horaria es opcional. Si elige una zona horaria, esta se guarda junto con el grupo de informes virtuales. En caso contrario, se usará la zona horaria del grupo de informes superior.  Al editar un grupo de informes virtual, la zona horaria guardada con el grupo de informes virtual aparece en el selector desplegable. Si el grupo de informes virtuales se creó antes de que se añadiera la opción de la zona horaria, en el selector desplegable se muestra la zona horaria del grupo de informes principal. |
| Segmentos | Solo tiene que añadir un segmento o apilar otros.   Nota: Al apilar dos segmentos, se unen de manera predeterminada con una instrucción AND. No es posible cambiarlo a una instrucción OR. Si intenta eliminar o modificar un segmento que se utilice en un grupo de informes virtuales, se muestra un error. |

## Definir la descripción de la visita

En la pestaña [!UICONTROL Descripción de la visita], defina esta configuración y haga clic en **[!UICONTROL Continuar]**.

![](assets/visit-definition.png)


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Ajustar una definición de visita](https://video.tv.adobe.com/v/3428472?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

| Elemento | Descripción |
| --- |--- |
| **Configuración de definición de visitas** |  |
| Habilitar el procesamiento del tiempo del informe | Use el procesamiento del tiempo del informe para cambiar la duración predeterminada del tiempo de espera de la visita. Esta configuración no es destructiva y se aplica solo en Analysis Workspace. [Más información](/help/components/vrs/vrs-report-time-processing.md) |
| Tiempo de espera de la visita | Define la cantidad de inactividad que debe tener un visitante único antes de que se inicie una nueva visita automáticamente. Esto afectará la métrica de visitas, el contenedor de segmentos de visita y los eVars que caducan en la visita. |
| Iniciar nueva visita con evento | Inicia una nueva sesión cuando cualquiera de los eventos especificados se activa independientemente de si una sesión ha excedido el tiempo de espera. |
| **Configuración de visitas a aplicaciones móviles** | Modifique cómo se definen las visitas para las visitas a aplicaciones móviles recopiladas por los SDK para móviles de Adobe. Esta configuración no es destructiva y se aplica solo en Analysis Workspace. |
| Evitar que las visitas en segundo plano generen una nueva visita individual | Evita que los resultados de fondo comiencen una nueva visita y que inflen las visitas y las métricas de visitante único. |
| Iniciar una nueva visita cada vez que se abre una aplicación | Se inicia una nueva sesión cuando se abre una aplicación. [Más información](/help/components/vrs/vrs-mobile-visit-processing.md) |

## Incluir y cambiar el nombre de los componentes

![](assets/components.png)

1. En la pestaña [!UICONTROL Componentes], active la casilla de verificación para aplicar la depuración para incluir, excluir y cambiar el nombre de los componentes de este grupo de informes virtuales en Analysis Workspace.
Para obtener más información sobre la revisión de grupos de informes virtuales, consulte [Revisión de componentes de grupos de informes virtuales](/help/components/vrs/vrs-components.md).

1. Arrastre los componentes (dimensiones, métricas, segmentos o intervalos de fechas) que desee incluir en el grupo de informes virtuales a la sección [!UICONTROL Componentes incluidos].

1. Cuando haya terminado, haga clic en **[!UICONTROL Guardar]**.

## Previsualización de datos

A la derecha de cada pestaña, puede previsualizar el total de visitas, visitas y visitantes en este grupo de informes virtuales, en comparación con el grupo de informes original.

## Ver compatibilidad del producto

Algunos productos de Adobe Analytics no admiten algunas funciones de los grupos de informes virtuales. La lista de compatibilidad del producto le permite ver qué productos de Adobe Analytics son compatibles en función de la configuración actual del grupo de informes virtuales.
