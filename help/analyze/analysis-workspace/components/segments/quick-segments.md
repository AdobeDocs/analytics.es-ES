---
description: Use segmentos rápidos en Analysis Workspace.
title: Segmentos rápidos
feature: Segmentation
role: User, Admin
exl-id: 680e7772-10d3-4448-b5bf-def3bc3429d2
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 99%

---

# Segmentos rápidos

Los segmentos rápidos permiten explorar fácilmente los datos de un proyecto determinado, sin necesidad de crear un segmento de lista de componentes más complejo en el [generador de segmentos ](/help/components/segmentation/segmentation-workflow/seg-build.md).

Tenga en cuenta lo siguiente al crear segmentos rápidos:

* Los segmentos rápidos solo se aplican al proyecto en el que se crearon. No están disponibles en otros proyectos y no se pueden compartir con otros usuarios. 
* Se permite un máximo de 3 reglas.
* No se admiten contenedores anidados ni reglas secuenciales.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentos rápidos](https://video.tv.adobe.com/v/345336?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Creación de un segmento rápido

Cualquier usuario de Analysis Workspace puede crear un segmento rápido.

Para crear un segmento rápido haga lo siguiente:

1. Elija uno de los siguientes métodos para empezar a crear el segmento rápido:

   * **Ad hoc (arrastrar y soltar):** desde el carril izquierdo, arrastre un componente a la zona de colocación de segmentos del encabezado de panel.

     ![colocar un segmento en la zona de colocación](assets/segment-dropzone.png)

     Puede editar el segmento como se describe en [Edición de segmentos rápidos](#edit-quick-segments).

     >[!NOTE]
     >
     > Al crear un segmento rápido ad hoc (arrastrar y soltar) tenga en cuenta lo siguiente:
     > * No se admiten los siguientes tipos de componentes: métricas y dimensiones calculadas, así como métricas a partir de las cuales no se pueden generar segmentos.
     > * Para las dimensiones y eventos completos, Analysis Workspace crea segmentos de visita del tipo “existe”. Ejemplos: `Hit where eVar1 exists` o `Hit where event1 exists`.
     > * Si se suelta “sin especificar” o “ninguno” en la zona de colocación de segmentos, se convierten automáticamente en un segmento “no existe”, para que se trate adecuadamente en los segmentos.


   * **Uso del icono de segmento:** en una tabla de forma libre, seleccione el icono **Segmento** en la cabecera del panel.

     ![Filtro de segmento](assets/quick-seg1.png)

1. Ajuste uno de los siguientes ajustes:

   | Configuración | Descripción |
   | --- | --- |
   | [!UICONTROL Nombre] | El nombre predeterminado de un segmento es una combinación de los nombres de reglas del segmento. Puede cambiar el nombre del segmento por otro más descriptivo. |
   | [!UICONTROL Incluir/excluir] | Puede incluir o excluir componentes en su definición de segmento, pero no ambas cosas. |
   | [!UICONTROL Contenedor de visita/visita individual/visitante] | Los segmentos rápidos incluyen solo un [contenedor de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=es#section_AF2A28BE92474DB386AE85743C71B2D6) que le permite incluir una dimensión, métrica o intervalo de fecha en el segmento (o excluirlo). [!UICONTROL Visitante] contiene datos globales específicos del visitante en las visitas y vistas de páginas. Un contenedor de [!UICONTROL Visita] le permite establecer reglas para desglosar los datos del visitante en función de las visitas, y un contenedor de [!UICONTROL Visita individual] le permite desglosar la información del visitante según las vistas de página individuales. El contenedor predeterminado es [!UICONTROL Visita individual]. |
   | [!UICONTROL Componentes] (dimensión/métrica/intervalo de fechas) | Defina hasta 3 reglas añadiendo componentes (dimensiones, métricas, intervalos de fechas o valores de dimensión). Existen tres formas de encontrar el componente correcto:<ul><li>Empiece a escribir y el generador de segmentos rápidos encontrará automáticamente el componente adecuado.</li><li>Utilice la lista desplegable para buscar el componente.</li><li>Arrástrelos y suéltelos desde el carril izquierdo.</li></ul> |
   | [!UICONTROL Operador] | Utilice el menú desplegable para buscar operadores estándar y operadores de [!UICONTROL recuento distintos]. Consulte [Operadores de segmento](/help/components/segmentation/seg-reference/seg-operators.md). |
   | Signo más (+) | Añadir otra regla |
   | Cualificadores AND/OR | Puede agregar calificadores AND u OR a las reglas, pero no puede combinar AND y OR en una sola definición de segmento. |
   | [!UICONTROL Aplicar] | Aplique este segmento al panel. Si el segmento no contiene datos, se le pregunta si desea continuar. |
   | [!UICONTROL Abrir creador] | Se abrirá el Generador de segmentos. Tras haber guardado o aplicado el segmento en el Generador de segmentos, ya no se considerará un “segmento rápido”. Forma parte de la biblioteca de segmentos de lista de componentes. <p>Para que el componente esté disponible en todos sus proyectos y en el carril izquierdo, seleccione la opción [!UICONTROL **Ponga este segmento a disposición de todos los proyectos y agréguelo a la lista de componentes**].</p><p>Para más información, consulte la sección [Guardar un segmento rápido como un segmento de lista de componentes](#save-a-quick-segment-as-a-component-list-segment) en este artículo.</p><p>**Nota:** Solo los usuarios con permiso de Creación de Segmentos en [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md) pueden abrir el Generador de Segmentos.</p> |
   | [!UICONTROL Cancelar] | Cancele este segmento rápido: (no lo aplique). |
   | [!UICONTROL Intervalo de fechas] | El validador utiliza el intervalo de fecha del panel para la búsqueda de datos. Sin embargo, cualquier intervalo de fechas aplicado en un segmento rápido anula el intervalo de fechas del panel en la parte superior del panel. |
   | Vista previa (parte superior derecha) | Le permite previsualizar las métricas clave para comprobar si tiene un segmento válido y ver su amplitud. Representa el desglose del conjunto de datos que verá cuando aplique este segmento. Podría recibir un aviso que indique que este segmento no tiene datos. En este caso, puede continuar o cambiar la definición del filtro. |

1. Seleccione [!UICONTROL **Aplicar**] para guardar los cambios.

## Edición de segmentos rápidos

1. Pase el ratón sobre el segmento rápido y seleccione el icono **Editar**.

   ![Edición de un filtro ad hoc](assets/filter-adhoc-edit.png)

1. Edite la definición del segmento o el nombre del segmento.

1. Seleccione [!UICONTROL **Aplicar**].

## Guardar un segmento rápido como un segmento de lista de componentes

>[!IMPORTANT]
>
> Tenga en cuenta lo siguiente al guardar un segmento rápido:
> 
> * Para guardar un segmento rápido, necesita el permiso de creación de segmentos en [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md).
> 
> * Después de guardar o aplicar el segmento, ya no se puede editar en el generador de segmentos rápidos. En su lugar, debe utilizar el Generador de segmentos normal.

Puede elegir guardar segmentos rápidos como segmentos de lista de componentes. Entre las ventajas de los segmentos de lista de componentes se incluyen:

* Disponibilidad en todos los proyectos de Workspace
* Admite segmentos más complejos, así como segmentos secuenciales

Puede guardar segmentos desde el Generador de segmentos rápidos o desde el [!UICONTROL Generador de filtros].

### Guardar en el generador de segmentos rápidos {#save2}

1. Tras aplicar el segmento rápido, pase el ratón sobre él y seleccione el icono de información (“i”).
1. Consulte **[!UICONTROL Poner a disposición de todos los proyectos y añadirlos a la lista de componentes]**.
1. (Opcional) Cambie el nombre del segmento.
1. Seleccione **[!UICONTROL Guardar]**.

   El segmento aparece ahora en la lista de componentes en el carril izquierdo. Además, observe que la barra lateral del segmento cambia de azul claro a un azul más oscuro, lo que indica que ya no puede editarse ni abrirse en el generador de segmentos rápidos.

### Guardar en el Generador de segmentos {#save3}

1. Tras aplicar el segmento rápido, pase el ratón sobre él y seleccione el icono de información (“i”).
1. Seleccione **[!UICONTROL Guardar segmento]**.
1. (Opcional) Cambie el nombre del segmento y, a continuación, seleccione [!UICONTROL **Aplicar**].

   Vuelva a Workspace y observe que la barra lateral del segmento cambia de azul claro a un azul más oscuro, lo que indica que ya no puede editarse ni abrirse en el generador de segmentos rápidos. Al guardarlo, pasa a formar parte de la lista de componentes.

Después de aplicar el segmento, puede elegir añadirlo a la lista de componentes del segmento y ponerlo a disposición de todos los proyectos.

1. Pase el ratón sobre el segmento guardado y seleccione el icono de lápiz.

1. Seleccione [!UICONTROL **Abrir generador**].

1. En la parte superior del Generador de segmentos, observe el diálogo [!UICONTROL **Segmento solo de proyecto**]:

   ![diálogo de segmento solo de proyecto](assets/project-only-segment-dialog.png)

1. Seleccione la casilla de verificación situada junto a **[!UICONTROL Poner a disposición de todos los proyectos y añadirlos a la lista de componentes.]**

1. Seleccione **[!UICONTROL Guardar]**.

   El segmento aparece ahora en la lista de componentes del segmento para todos los proyectos.
También puede [compartir el segmento](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=es#concept_4A9726927E7C44AFA260E2BB2721AFC6) con otras personas de su organización.

## Ejemplo de segmento rápido

Este es un ejemplo de un segmento que combina dimensiones y métricas:

![](assets/quick-seg2.png)

## Problema conocido

1. Cree un segmento rápido con 2 entradas y haga clic en **[!UICONTROL Guardar]** como Prueba1.
1. Haga clic en **[!UICONTROL Guardar como]** y guarde este segmento rápido como Prueba2.
1. Edite el segmento rápido Prueba2 y vuelva a guardarlo como Prueba2.
Observe que Prueba2 modifica el segmento rápido Prueba1.
