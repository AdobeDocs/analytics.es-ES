---
title: Variables de lista
description: Cree y configure variables de lista para usar en sistema de informes.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 25%

---

# Variables de lista

Cree y configure variables de lista para usar en sistema de informes. Establezca sus valores de delimitador, caducidad, asignación y máximo. Recopilar datos para variables de lista usando [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Variables de lista]**

* **[!UICONTROL Nombre]**: Nombre de la variable de lista. Este nombre es la etiqueta de dimensión en Analysis Workspace.

* **[!UICONTROL Estado]**: habilita o deshabilita la recopilación de datos para esta variable. Si una variable está deshabilitada, no se recopilan datos, aunque la implementación envíe datos a esa variable.

* **[!UICONTROL Delimitador de valores]**: El carácter usado para separar valores dentro de la variable de lista. Normalmente, se trata de caracteres como comas, dos puntos, barras verticales o algo similar. Los caracteres de bytes múltiples no se admiten como delimitadores en variables de lista.

* **[!UICONTROL Caduca después de]**: de forma similar a la caducidad de eVar, este campo determina la cantidad de tiempo que puede pasar entre la variable de lista y el evento de conversión para que se relacionen.
   * **En una vista de página o nivel de visita**: Los eventos de éxito más allá de la vista de página o la visita no se vincularían de nuevo a ningún valor dentro de la variable de lista.
   * **Basado en un período de tiempo, como día, semana, mes, etc**: Los eventos de éxito que superen el período de tiempo especificado no se vincularán de nuevo a ningún valor dentro de la variable de lista. También se puede definir un número de días personalizado.
   * **Eventos de conversión específicos**: Los demás eventos de éxito que se activen después de designar el evento específico no se vincularán de nuevo a ningún valor de la variable de lista.
   * **Nunca**: Puede pasar cualquier cantidad de tiempo entre la variable de lista y el evento de éxito.

* **[!UICONTROL Asignación]**: Esta opción determina cómo dividirán los eventos de éxito el crédito entre los valores:
   * **Total**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el total del crédito por los eventos de éxito.
   * **Lineal**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el crédito dividido entre los eventos de conversión.
   * Los valores de variable no se sobrescriben nunca; se suman a los valores que obtienen el crédito por los eventos de éxito.

* **[!UICONTROL Descripción]**: Una descripción de cómo su organización utiliza la variable de lista.

* **[!UICONTROL Valores máximos]**: Designa el número de valores activos permitidos para esta variable de lista. Por ejemplo, si se establece en 3, solo se guardarán los últimos 3 valores capturados y se descartarán todos los capturados con anterioridad. Tenga en cuenta que si se envían varios valores para la misma variable de lista en la misma visita y ha restringido el uso de valores máximos, cada valor tendrá la misma marca de tiempo y no se garantiza qué valor se guarde. Si un visitante mantiene más valores que el máximo permitido, se utilizan los valores más recientes. Se permiten hasta 250 valores máximos.

  Esta configuración es útil para limitar la atribución a un número específico de valores. Por ejemplo, si una variable de lista se establece en `"A,B,C"` en la primera página de una visita y, a continuación, se establece en `"X,Y,Z"` en la página siguiente, la atribución se distribuye a estos seis valores en función de su asignación. Si desea limitar la atribución a solo `"X,Y,Z"`, puede establecer el máximo de valores en tres.
