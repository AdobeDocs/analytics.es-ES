---
description: Aprenda a depurar proyectos en Analysis Workspace. La depuración limita el acceso a los componentes antes de compartir un proyecto.
keywords: Revisión de Analysis Workspace
title: Depurar proyectos
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
TQID: https://experienceleague.adobe.com/91rBra7P-oB7zHq0VLyG48uANjv2ZcmcTpN-pc3W5MY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 548
ht-degree: 75%

---

# Depurar proyectos de

La depuración permite limitar los componentes (dimensiones, métricas, segmentos e intervalos de fechas) antes de compartir un proyecto. Cuando un destinatario abre el proyecto, verá un conjunto limitado de componentes que ha seleccionado para ellos. La depuración es un paso opcional pero recomendado antes de compartir un proyecto.

>[!NOTE]
> Los perfiles de productos son el mecanismo principal que controla los componentes que puede ver un usuario. Se administran mediante Adobe CX Enterprise Admin Console. La depuración es un filtro secundario.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Depurar proyectos](https://video.tv.adobe.com/v/24711?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Aplicar depuración de proyecto

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos del proyecto]**.
Los componentes que se utilizan en el proyecto se añadirán automáticamente.
Si un proyecto tiene varios grupos de informes, verá un destino de colocación depurada para cada grupo de informes en el proyecto.
1. (Opcional) Para agregar más componentes, arrastre los componentes que desee compartir desde el panel izquierdo a la zona de colocación **[!UICONTROL Depurar componentes]** para el grupo de informes.
1. Seleccione **[!UICONTROL Listo]**.


![](assets/curation-field.png)

Cuando un destinatario abre un proyecto depurado, solo verá el conjunto depurado de componentes que haya definido:


## Eliminar depuración del proyecto

Para eliminar la depuración del proyecto y restaurar el conjunto completo de componentes en el carril izquierdo:

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos del proyecto]**.
1. Haga clic en **[!UICONTROL Eliminar depuración]**.
1. Seleccione **[!UICONTROL Listo]**.

## Depuración del grupo de informes virtuales

Para aplicar la depuración a nivel de grupo de informes, de modo que se aplique a muchos proyectos a la vez, puede [depurar componentes en un grupo de informes virtuales](/help/components/vrs/vrs-components.md).

>[!NOTE]
>
> La depuración de grupos de informes virtuales siempre se aplica antes de la depuración de proyectos. Aunque el proyecto depurado incluya determinados componentes, se filtrarán si el grupo de informes virtuales depurado no incluye estos componentes.
> 

## Opciones de depuración de componentes

En un proyecto depurado o grupo de informes virtuales, el destinatario tiene la opción de **[!UICONTROL Mostrar todos]** los componentes en el carril izquierdo. [!UICONTROL Mostrar todo] revela diferentes conjuntos de componentes, según:

* Nivel de permiso del usuario (administrador o no administrador)
* Función del proyecto (propietario/editor o no)
* Tipo de depuración aplicada (grupo de informes virtual o proyecto)
* Componentes propiedad del usuario o que el usuario ha compartido. Entre los componentes propios o compartidos se incluyen los segmentos, las métricas calculadas y los intervalos de fechas. No incluyen componentes implementados, como eVars, props y eventos personalizados.

Nota: Las funciones de vista que no son de administración no tendrán acceso al carril izquierdo del proyecto, por lo que se han omitido de la tabla siguiente.

| Tipo de depuración | Administradores | Propietario del proyecto no administrador o función de edición | Función duplicada no perteneciente a administración |
|---|---|---|---|
| **Grupo de informes virtuales depurado** | Todos los componentes no depurados del grupo de informes virtuales | Componentes de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función | Componentes de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |
| **Proyecto depurado** | Todos los componentes de proyecto no depurados | Todos los componentes de proyecto no depurados | Componentes de proyecto no depurados que pertenecen a esta función o que se compartieron con esta función |
| **Proyecto depurado en un grupo de informes virtuales depurado** | Todos los componentes no depurados, mostrados bajo **[!UICONTROL Componentes de proyecto no depurados]** y **[!UICONTROL Componentes de grupos de informes virtuales no depurados]** | Todos los componentes no depurados del proyecto Y los componentes no depurados del grupo de informes virtuales que pertenezcan a esta función o que hayan sido compartidos con ellos | Grupo de informes virtuales y componentes de proyecto no depurados que pertenecen a esta función o que han sido compartidos con ellos |
