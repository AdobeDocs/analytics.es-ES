---
title: Variables de lista
description: Cree y configure variables de lista para usar en sistema de informes.
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 100%

---


# Variables de lista

Cree y configure variables de lista para usar en sistema de informes. Defina aquí sus valores de delimitador, caducidad, asignación y máximo.

Puede acceder a la configuración en Admin Console:

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]**.
2. Seleccione el grupo de informes.
3. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Lista de variables]**.

* **Nombre**: Cada valor delimitado puede contener un máximo de 255 caracteres (o menos si se utilizan caracteres multibyte). Esta es la longitud máxima de cada elemento.
* **Delimitador de valores**: carácter utilizado para separar valores en una variable de lista. Normalmente son caracteres como comas, dos puntos, barras verticales o algún otro similar.

   >[!NOTE] Los caracteres de bytes múltiples no se admiten como delimitadores en variables de lista. El delimitador debe ser de un solo byte.

* **Caducidad**: similar a la caducidad de eVar, determina la cantidad de tiempo que puede transcurrir entre la variable de lista y el evento de conversión para que se relacionen.
   * **A nivel de vista de página o visita**: Los eventos de éxito más allá de la vista de página o la visita no se vincularán con ningún valor que haya dentro de la variable de lista.
   * **En función de un período de tiempo como día, semana, mes, etc.**: Los eventos de éxito que no entren dentro del período de tiempo especificado no se vincularán a ningún valor que haya dentro de la variable de lista. También se puede definir un número de días personalizado.
   * **Eventos de conversión específicos**: Cualquier otro evento de éxito que se active después del evento específico designado no se vinculará con ningún valor que haya dentro de la variable de lista.
   * **Nunca**: Puede transcurrir cualquier cantidad de tiempo entre la variable de lista y el evento de éxito.

* **Asignación**: Esta opción determina cómo dividirán los eventos de éxito el crédito entre los valores:
   * **Total**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el total del crédito por los eventos de éxito.
   * **Lineal**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el crédito dividido entre los eventos de conversión.
   * Los valores de variable no se sobrescriben nunca; se suman a los valores que obtienen el crédito por los eventos de éxito.

* **Valores máximos**: Designa el número de valores activos permitidos para esta variable de lista. Por ejemplo, si se establece en 3, solo se guardarán los últimos 3 valores capturados y se descartarán todos los capturados con anterioridad. Tenga en cuenta que si se envían varios valores para la misma variable de lista en la misma visita y se ha restringido el uso de los valores máximos, todos los valores adquirirán la misma marca de tiempo y no puede garantizarse qué valor se guardará.

Se almacena un límite de 250 valores máximos una vez por visitante. Si se exceden los 250 valores por visitante, se utilizan los últimos 250 valores. La caducidad de estos valores está basada en la caducidad configurada para la variable.

La opción Valores máximos resulta muy útil para limitar la atribución a un número específico de valores. Por ejemplo, si una variable de lista se establece en &quot;A,B,C&quot; en la primera página de una visita y en &quot;X,Y,Z&quot; en la página siguiente, la atribución se distribuye a estos seis valores en función de la asignación. Si desea limitar la atribución a &quot;X,Y,Z&quot; exclusivamente, puede establecer los valores máximos en tres.
