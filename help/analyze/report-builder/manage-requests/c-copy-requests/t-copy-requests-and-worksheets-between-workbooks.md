---
description: Se puede copiar una hoja de cálculo completa de un libro de origen en una hoja de cálculo de uno o varios libros de destino.
seo-description: Se puede copiar una hoja de cálculo completa de un libro de origen en una hoja de cálculo de uno o varios libros de destino.
seo-title: Copia de solicitudes y hojas de cálculo entre libros
solution: Analytics
title: Copia de solicitudes y hojas de cálculo entre libros
topic: Creador de informes
uuid: 6 b 2 c 4259-d 8 cb -430 e -819 f -38 e 213 dd 2661
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copia de solicitudes y hojas de cálculo entre libros

Se puede copiar una hoja de cálculo completa de un libro de origen en una hoja de cálculo de uno o varios libros de destino.

Para ello, debe tener al menos dos libros abiertos en la misma instancia de Excel: el primer libro de origen contiene la hoja de cálculo con solicitudes asignadas a celdas, mientras que el resto de libros adicionales constituyen el destino. En los libros de destino debe Inicie sesión en el mismo grupo de informes que el libro de origen; de lo contrario, no podrá pegar hojas de cálculo que contengan solicitudes.
1. Haga clic con el botón derecho en la hoja de cálculo del libro de origen y seleccione **[!UICONTROL Copiar hoja de cálculo con solicitudes]**.
1. En el libro de destino, haga clic con el botón derecho en la hoja de cálculo y seleccione **[!UICONTROL Pegar hoja de cálculo con solicitudes]**.

   La misma instancia de Excel significa que un único proceso de Excel ([!DNL excel.exe]) se ejecuta en el equipo al mismo tiempo. Si se inician dos instancias de Excel y se intenta copiar una hoja de cálculo de un libro de la primera instancia de Excel en un libro en la segunda instancia, la opción para pegar una hoja de cálculo no estará presente en el menú contextual del Creador de informes de la segunda instancia de Excel.

   Si se inicia la sesión en los libros de origen y de destino utilizando distintos grupos de informes, los únicos resultados que se verán de la operación de pegado serán los que afecten al formato del libro de destino. El Creador de informes muestra un mensaje que indica que la información de las solicitudes derivadas de un grupo de informes especificado (en el libro de origen) no está disponible en el libro de destino. Para mostrar las solicitudes pegadas en el libro de destino, se debe iniciar la sesión en el libro de destino utilizando el mismo grupo de informes que el libro de origen.

   Se pueden copiar y pegar una o varias solicitudes de una hoja de cálculo de un libro en una hoja de cálculo de otro libro, siempre que el segundo libro esté abierto como otro documento en la misma instancia de Excel. Las solicitudes de ambos libros se deben crear utilizando el mismo inicio de sesión del grupo de informes.
