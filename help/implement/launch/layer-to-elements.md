---
description: 'null'
title: Asignar objetos de capa de datos a elementos de datos
uuid: null
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Asignar objetos de capa de datos a elementos de datos


Después de [crear una capa](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) de datos para la implementación, puede asignar objetos dentro de ella a elementos [de datos en Launch](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element). Los elementos de datos son componentes básicos de su mapa de datos que se pueden aprovechar de varias formas. Puede utilizar elementos de datos para recopilar, organizar y entregar datos en las soluciones de la plataforma de Adobe, incluidos los informes de Analytics.

Para asignar objetos de capa de datos a elementos de datos de lanzamiento:

1. En Iniciar, haga clic en el nombre de la propiedad a la que desea agregar el elemento de datos. Si todavía no ha configurado una propiedad, consulte las instrucciones para [crear una propiedad](https://docs.adobe.com/content/help/en/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch.html)de inicio.

2. Click **Data Elements** and then click **Create New Data Element**.

   ![crear elemento de datos](assets/createelement.png)


3. Escriba un nombre para el elemento de datos. Este nombre debe ser una etiqueta simple que corresponda a una variable JavaScript de la capa de datos que desee rastrear.

4. En Extensión, seleccione **Principal.** Esta extensión incluye todas las variables que necesitará.

5. For **Data Element Type**, select **JavaScript Variable**. Escriba el nombre **de la variable** Javascript en el campo correspondiente. Debe coincidir con el nombre exacto del objeto en la capa de datos JavaScript.

6. En Valor **** predeterminado, introduzca cualquier valor que desee establecer de forma predeterminada o déjelo en blanco si corresponde.

7. Según sus prácticas, puede seleccionar las opciones para forzar valores en minúsculas y aplicar texto limpio (Launch aplicará espaciado convencional).

8. Especifique la duración durante la cual desea que Launch almacene valores para el nuevo elemento de datos.

9. Haga clic en **Guardar**.

El siguiente ejemplo muestra un elemento de datos Nombre de página en Launch creado para la variable JavaScript ``pageName`` en la capa de datos:

![Especificar elemento](assets/new_element.png)


Con los objetos de capa de datos asignados a elementos de datos, puede aprovecharlos para rellenar variables de Analytics. Para obtener más información, consulte [Asignación de elementos de datos a variables](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)de Analytics.
