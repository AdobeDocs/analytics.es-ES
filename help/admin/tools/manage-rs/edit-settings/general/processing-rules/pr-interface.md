---
title: Interfaz de reglas de procesamiento
description: Navegue por la interfaz para crear, editar o eliminar reglas de procesamiento.
feature: Processing Rules
role: Admin
exl-id: 897d2bb6-cc10-43b1-b436-20985d24d998
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Interfaz de reglas de procesamiento

La interfaz de reglas de procesamiento permite crear, editar o eliminar reglas de procesamiento.

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de procesamiento]**

>[!WARNING]
>
>Las reglas de procesamiento afectan directamente a la recopilación de datos y pueden causar pérdida de datos si se utilizan incorrectamente. Pruebe siempre las reglas de procesamiento en un grupo de informes de desarrollo antes de habilitarlas en un grupo de informes de producción para mitigar los problemas de calidad de los datos.

## Estructura general

Esta interfaz contiene dos componentes principales:

* **[!UICONTROL Orden de procesamiento]**: Las reglas se ejecutan exactamente en el orden especificado, a partir de la regla 1. Cada visita se ejecuta mediante cada regla; no hay condiciones de finalización anticipada. Asegúrese de que las condiciones de cada regla de procesamiento admiten cada visita enviada al grupo de informes.
* **[!UICONTROL Conjuntos de reglas]**: Las definiciones de cada una de sus reglas de procesamiento.

Puede tener hasta 150 reglas de procesamiento y hasta 30 condiciones por regla de procesamiento. No hay un límite razonable para el número de acciones por regla de procesamiento.

## Estructura del conjunto de reglas

Cada regla de procesamiento contiene las siguientes secciones:

* **Título de regla**: La etiqueta de la regla. No afecta a la lógica de las reglas de procesamiento, pero resulta útil para realizar un seguimiento de lo que hace la regla.
* **Condición**: se muestra como texto, &quot;[!UICONTROL Si alguna/todas las condiciones siguientes son verdaderas]&quot;. Si no incluye una condición, la regla siempre se ejecuta en cada visita.
* **Acción**: si no existe ninguna condición, el texto se muestra como &quot;[!UICONTROL Ejecutar siempre]&quot;. Si existe una condición, el texto se muestra como &quot;[!UICONTROL Luego haga lo siguiente]&quot;. Si la condición anterior se evalúa como `true`, todas las acciones enumeradas en esta sección se ejecutarán potencialmente. Además de la condición de una regla, _también_ puede adjuntar condiciones a acciones individuales. Estas son las acciones disponibles:
   * **[!UICONTROL Sobrescribir valor de]**: sobrescribe la variable deseada con otra variable, un valor estático o un valor concatenado.
   * **[!UICONTROL Eliminar valor de]**: elimina el valor de variable deseado para esa visita.
   * **[!UICONTROL Definir evento]**: almacena en Déclencheur el evento deseado. Normalmente, establecería eventos en un valor personalizado de `1`; también se permite establecer eventos en valores distintos de `1` o incluso establecerlos en valores establecidos en variables de datos de contexto.
* **De lo contrario, acción**: Si existe una condición, esta sección aparece como &quot;[!UICONTROL De lo contrario, realice lo siguiente]&quot;. Si la condición anterior se evalúa como `false`, todas las acciones enumeradas en esta sección se ejecutarán potencialmente. Esta sección sigue las mismas acciones de regla que se han indicado anteriormente, incluida la capacidad de sobrescribir valores, eliminar valores y establecer eventos.
* **Motivo**: registre quién solicitó la regla y de qué depende. No afecta a la lógica de las reglas de procesamiento, pero resulta útil para realizar un seguimiento de por qué existe la regla.

Consulte [Dimensiones y métricas disponibles para las reglas de procesamiento](pr-variables.md) para obtener una lista completa de las variables que puede usar en esta interfaz.

* Cualquier variable que permita &quot;Read&quot; puede utilizarse en una condición.
* Cualquier variable que permita &quot;Write&quot; puede utilizarse en una acción.
