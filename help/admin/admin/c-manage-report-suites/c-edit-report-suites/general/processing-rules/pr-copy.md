---
title: Copiar reglas de procesamiento
description: Obtenga información sobre cómo copiar reglas de procesamiento de un grupo de informes a otro.
feature: Processing Rules
role: Admin
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Copiar reglas de procesamiento entre grupos de informes

Copiar reglas de procesamiento le evita volver a crear manualmente la misma lógica en varios grupos de informes. Puede utilizar la función de copia para compartir fácilmente la funcionalidad de reglas de procesamiento en muchos grupos de informes, o para copiar la funcionalidad probada de un grupo de informes de desarrollo a un grupo de informes de producción.

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de procesamiento]** > **[!UICONTROL Copiar reglas de procesamiento]**

Esta interfaz permite dos opciones:

* **Reemplazar todas las reglas de procesamiento**: Esta opción elimina todas las reglas de procesamiento del grupo de informes de destino y, a continuación, agrega todas las reglas de procesamiento al grupo de informes de destino en el mismo orden. No se puede seleccionar un número limitado de reglas de procesamiento para reemplazar.
* **Anexar reglas de procesamiento específicas**: esta opción le permite seleccionar una o más reglas de procesamiento. Las reglas anexadas se agregan al final de la lista de reglas de procesamiento en cada grupo de informes de destino. Tenga en cuenta el orden de las reglas de procesamiento y las reglas que ya existen al anexar reglas a cada grupo de informes de destino.

Al seleccionar reglas de procesamiento para anexar o grupos de informes a los que copiar, puede utilizar `Ctrl`/`Cmd` + `Click` para seleccionar varias reglas de procesamiento o grupos de informes. Una vez que seleccione los grupos de informes a los que desee copiar, seleccione **[!UICONTROL Copiar]** y confirme la ventana modal que aparece.

>[!WARNING]
>
>Las reglas de procesamiento afectan directamente a la recopilación de datos y pueden causar pérdida de datos si se utilizan incorrectamente. Pruebe siempre las reglas de procesamiento en un grupo de informes de desarrollo antes de copiarlas en un grupo de informes de producción para mitigar los problemas de calidad de los datos.
