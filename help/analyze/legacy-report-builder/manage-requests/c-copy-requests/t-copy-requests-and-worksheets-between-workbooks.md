---
description: Obtenga información sobre cómo copiar una hoja de cálculo de un libro de origen en uno o varios libros de destino.
title: Cómo copiar solicitudes y hojas de cálculo entre libros
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 54%

---

# Copiar solicitudes y hojas de cálculo entre libros

{{legacy-arb}}

Copiar una hoja de cálculo completa de un libro de origen en una hoja de cálculo de uno o varios libros de destino. Para ello, debe tener al menos dos libros abiertos en la misma instancia de Excel:

* El primer libro de origen contiene una hoja de cálculo (hoja de cálculo) con solicitudes asignadas a celdas.

* Los libros de destino adicionales son los destinos. Para cada nuevo libro de destino, debe iniciar sesión en el mismo grupo de informes que el libro de origen antes de poder pegar hojas de cálculo que contengan solicitudes.

>[!NOTE]
>
>Debe iniciar sesión en el libro de destino utilizando el mismo grupo de informes que el libro de origen. Las solicitudes de ambos libros se deben crear utilizando el mismo inicio de sesión del grupo de informes.

1. Haga clic con el botón derecho en la hoja de cálculo del libro de origen y seleccione **[!UICONTROL Copiar hoja de cálculo con solicitudes]**.
1. En el libro de destino, haga clic con el botón derecho en la hoja de cálculo y seleccione **[!UICONTROL Pegar hoja de cálculo con solicitudes]**.

   La misma instancia de Excel significa que un único proceso de Excel ([!DNL excel.exe]) se ejecuta en el equipo al mismo tiempo. Si se inician dos instancias de Excel y se intenta copiar una hoja de cálculo de un libro en la primera instancia de Excel en un libro en la segunda instancia, Report Builder no presenta la opción de pegar una hoja de cálculo en el menú contextual de la segunda instancia de Excel.

   Si se inicia la sesión en los libros de origen y de destino utilizando distintos grupos de informes, los únicos resultados que se verán de la operación de pegado serán los que afecten al formato del libro de destino. Report Builder muestra un mensaje que indica que la información de las solicitudes derivadas de un grupo de informes especificado (en el libro de origen) no está disponible en el libro de destino. Para mostrar las solicitudes pegadas en el libro de destino, se debe iniciar la sesión en el libro de destino utilizando el mismo grupo de informes que el libro de origen.

   Se pueden copiar y pegar una o varias solicitudes de una hoja de cálculo de un libro en una hoja de cálculo de otro libro, siempre que el segundo libro esté abierto como otro documento en la misma instancia de Excel. Las solicitudes de ambos libros se deben crear utilizando el mismo inicio de sesión del grupo de informes.
