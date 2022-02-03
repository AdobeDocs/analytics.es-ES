---
title: Crear anotaciones
description: Cómo crear anotaciones en Workspace.
role: User, Admin
source-git-commit: 6b5fd4e25056d7efbf3119a4d55d2e0a7897965f
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 3%

---


# Crear anotaciones

>[!NOTE]
>
>Actualmente, esta función está en prueba limitada.

1. Para crear anotaciones, tiene 4 formas de empezar:

   * Vaya a [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Anotación]. Se abre la página Administrador de anotaciones . Haga clic en [!UICONTROL Crear nueva anotación] y se abre el Generador de anotaciones.

   * Haga clic con el botón derecho en un punto de una tabla o en un gráfico de líneas. Se abre el Generador de anotaciones. Tenga en cuenta que, de forma predeterminada, las anotaciones creadas de esta forma solo son visibles en el proyecto en el que se crearon. Pero puede ponerlos a disposición de todos los proyectos.

   * En Workspace, vaya a [!UICONTROL Componentes] > [!UICONTROL Crear anotación]. Se abre el Generador de anotaciones.

   * Utilice esta tecla de acceso directo para abrir el Generador de anotaciones:
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. Rellene los elementos del Creador de anotaciones.

   ![](assets/ann-builder.png)

   | Elemento | Descripción |
   | --- | --- |
   | [!UICONTROL Título] | Asigne un nombre a la anotación, por ejemplo: &quot;Día de la memoria&quot; |
   | [!UICONTROL Descripción] | (Opcional) Proporcione una descripción para la anotación, por ejemplo: &quot;Fiesta pública observada en Estados Unidos&quot;. |
   | [!UICONTROL Etiquetas] | (Opcional) Organice las anotaciones creando o aplicando una etiqueta. |
   | [!UICONTROL Fecha de aplicación] | Seleccione la fecha o el intervalo de fechas que debe estar presente para que la anotación sea visible. |
   | [!UICONTROL Color] | Aplicar un color a la anotación. La anotación aparece en el proyecto con el color seleccionado. El color se puede utilizar para categorizar anotaciones, como festivos, eventos externos, problemas de seguimiento, etc. |
   | [!UICONTROL Ámbito] | (Opcional) Arrastre y suelte las métricas de déclencheur de la anotación. A continuación, arrastre y suelte las dimensiones o segmentos que actúen como filtros (es decir, con los que la anotación será visible). Si no especifica un ámbito, la anotación se aplicará a todos los datos.<ul><li>**[!UICONTROL Cualquiera de estas métricas está presente]**: Arrastre y suelte hasta 10 métricas que almacenarán en déclencheur la anotación para mostrar.</li><li>**[!UICONTROL Con todos estos filtros]**: Arrastre y suelte hasta 10 dimensiones o segmentos que filtrarán cuando se muestre la anotación.</li></ul><p>Casos de uso: Un eVar ha dejado de recopilar datos para un intervalo de fechas específico. Arrastre el eVar a la **[!UICONTROL Cualquiera de estas métricas está presente]** diálogo. O [!UICONTROL Visitas] no genera informes de ningún dato; siga el mismo proceso. |
   | [!UICONTROL Aplicar a todos los conjuntos de informes] | De forma predeterminada, la anotación se aplica al grupo de informes de origen. Al marcar esta casilla, puede hacer que la anotación se aplique a todos los grupos de informes de la empresa. |
   | [!UICONTROL Aplicar a todos los proyectos] | De forma predeterminada, la anotación se aplica al proyecto actual. Al marcar esta casilla, puede hacer que la anotación se aplique a todos los proyectos que posea. Tenga en cuenta que esta casilla de verificación solo aparece al iniciar el Generador de anotaciones desde el Creador de anotaciones? |

1. Haga clic en [!UICONTROL Guardar].

## Crear anotaciones a partir de un [!UICONTROL Línea] gráfico

1. Desde dentro de un [!UICONTROL Línea] gráfico, seleccione una caída o un pico en el [!UICONTROL Línea] y haga clic con el botón derecho en ella. Un elemento emergente llamado **[!UICONTROL Anotar selección]** aparece.

   ![](assets/annotate-line.png)

1. Haga clic en **[!UICONTROL Anotar selección]**. Se abre el Generador de anotaciones.

>[!NOTE]
>
>Observe la anotación de solo proyecto. Para que la anotación esté disponible para todos los proyectos, marque la casilla .

1. Complete los detalles como se ha especificado anteriormente. Observe que las fechas y cualquier métrica, etc., ya se han rellenado.

## Crear una anotación desde una tabla improvisada

1. Continúe como lo haría para un gráfico de líneas, pero haga clic con el botón derecho en una fila de la tabla que tenga que anotarse.

1. Select **[!UICONTROL Crear anotación a partir de una selección]**.

   ![](assets/annotate-table.png)

1. Complete los detalles como se ha especificado anteriormente. Observe que las fechas y cualquier métrica, etc., ya se han rellenado.

