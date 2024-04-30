---
title: Variables de lista
description: Cree y configure variables de lista para usar en sistema de informes.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 25%

---

# Variables de lista

Cree y configure variables de lista para usar en sistema de informes. Establezca sus valores de delimitador, caducidad, asignación y máximo. Recopilación de datos para variables de lista mediante [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL variables de lista]**

* **[!UICONTROL Nombre]**: Nombre de la variable de lista. Este nombre es la etiqueta de dimensión en Analysis Workspace.

* **[!UICONTROL Estado]**: habilite o deshabilite la recopilación de datos para esta variable. Si una variable está deshabilitada, no se recopilan datos, aunque la implementación envíe datos a esa variable.

* **[!UICONTROL Delimitador de valores]**: Carácter utilizado para separar valores dentro de la variable de lista. Normalmente, se trata de caracteres como comas, dos puntos, barras verticales o algo similar. Los caracteres de bytes múltiples no se admiten como delimitadores en variables de lista.

* **[!UICONTROL Caduca después de]**: similar a la caducidad del eVar, este campo determina la cantidad de tiempo que puede transcurrir entre la variable de lista y el evento de conversión para que se relacionen.
   * **A nivel de visita o vista de página**: Los eventos de éxito más allá de la vista de página o la visita no se vinculaban de nuevo a ningún valor dentro de la variable de lista.
   * **En función de un período de tiempo como día, semana, mes, etc**: los eventos de éxito que no entren en el período de tiempo especificado no se vincularán de nuevo a ningún valor de la variable de lista. También se puede definir un número de días personalizado.
   * **Eventos de conversión específicos**: Cualquier otro evento de éxito que se active después del evento específico designado no se vinculará de nuevo a ningún valor dentro de la variable de lista.
   * **Nunca**: Puede pasar cualquier cantidad de tiempo entre la variable de lista y el evento de éxito.

* **[!UICONTROL Asignación]**: Esta opción determina cómo dividirán los eventos de éxito el crédito entre los valores:
   * **Total**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el total del crédito por los eventos de éxito.
   * **Lineal**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el crédito dividido entre los eventos de conversión.
   * Los valores de variable no se sobrescriben nunca; se suman a los valores que obtienen el crédito por los eventos de éxito.

* **[!UICONTROL Descripción]**: una descripción de cómo su organización utiliza la variable de lista.

* **[!UICONTROL Valores máximos]**: Designa el número de valores activos permitidos para esta variable de lista. Por ejemplo, si se establece en 3, solo se guardarán los últimos 3 valores capturados y se descartarán todos los capturados con anterioridad. Tenga en cuenta que si se envían varios valores para la misma variable de lista en la misma visita y ha restringido el uso de valores máximos, cada valor tendrá la misma marca de tiempo y no se garantiza qué valor se guarde. Si un visitante mantiene más valores que el máximo permitido, se utilizan los valores más recientes. Se permiten hasta 250 valores máximos.

  Esta configuración es útil para limitar la atribución a un número específico de valores. Por ejemplo, si una variable de lista está configurada como `"A,B,C"` en la primera página de una visita y, a continuación, establezca en `"X,Y,Z"` en la página siguiente, la atribución se distribuye a estos seis valores en función de su asignación. Si desea limitar la atribución únicamente a `"X,Y,Z"`, puede establecer los valores máximos en tres.
