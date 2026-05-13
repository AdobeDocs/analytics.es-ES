---
description: Limitaciones al usar Report Builder y Power BI de Microsoft.
title: Limitaciones y especificaciones
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
TQID: https://experienceleague.adobe.com/L3R3ufcclrTpw-fKoFLD8Y-v56rTm4tXlXqjaTdmdoQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 631
ht-degree: 34%

---

# Limitaciones y especificaciones

{{legacy-arb}}

## Restricciones de publicación de Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Estas restricciones se aplican únicamente a la opción Publicar solicitudes de Report Builder como tablas de conjuntos de datos de Power BI.

* Se puede exportar a Power BI un máximo de 100 solicitudes de Report Builder por cada libro.
* El proceso de programación dejará de exportar solicitudes cuando se alcance la solicitud 101.
* Solo las primeras 10 000 filas de datos de Analytics se enviarán a Power BI por cada solicitud de Report Builder. Las filas restantes se ignorarán.

## Editar una solicitud de Report Builder después de publicar en Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Esta especificación se aplica a las opciones Publicar todas las solicitudes de Report Builder como tablas de conjunto de datos de Power BI y Publicar todas las tablas con formato en el libro como tablas de conjuntos de datos de Power BI.

Editar una solicitud de Report Builder tras su publicación en Power BI puede causar problemas.

* **Caso 1**: Publica un libro en Power BI y crea una visualización basada en sus datos. A continuación, realice cambios en el libro, lo que hará que desaparezca una de las columnas del conjunto de datos a las que hace referencia. A continuación, vuelva a publicar. Esto interrumpirá la visualización en Power BI.

  **Aquí tiene un ejemplo de cómo se romperá la visualización:**

   1. En Report Builder, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   2. Programe esta solicitud para que se publique en Power BI.
   3. En Power BI, cree una visualización para Página y Vistas de página.
   4. Ahora edite el libro eliminando Vistas de página de la solicitud.
   5. Edite la programación con el libro actualizado y vuelva a publicar la solicitud en Power BI.
   6. Una vez enviado el nuevo libro a Power BI

      1. Compruebe que sobrescribió el conjunto de datos existente que se creó cuando publicó por primera vez.
      2. Compruebe que la tabla page_1 se actualiza correctamente con las columnas Página y Visitas.
      3. Compruebe que la visualización esté rota, ya que hace referencia a la columna Vistas de página que ya no está presente en la tabla page_1.

  **A continuación se muestra un ejemplo de cómo NO se interrumpirá la visualización:**

   1. En Report Builder, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   2. Programe esta solicitud para que se publique en Power BI.
   3. En Power BI, cree una visualización para Página y Vistas de página.
   4. Ahora, edite el libro en Report Builder agregando la métrica Visitas y conservando Página y Vistas de página.
   5. Edite la programación con el libro actualizado y vuelva a publicar la solicitud en Power BI.
   6. Una vez enviado el nuevo libro a Power BI

      1. Compruebe que sobrescribió el conjunto de datos existente que se creó cuando publicó por primera vez.
      2. Compruebe que la tabla page_1 se actualiza correctamente con las columnas Página, Vistas de página y Visitas.
      3. Compruebe que la visualización sigue funcionando correctamente, ya que hace referencia a dos columnas que siguen presentes en la tabla page_1.

* **Caso 2**: Se fija una sección del libro a un panel de Power BI y posteriormente se quita esa sección anclada (como un gráfico o una tabla) del libro. Esto interrumpirá la visualización.

## Cambio de nombre de un informe de Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

De forma predeterminada, el nombre se rellena con el nombre de archivo del libro (sin la extensión .xlsx), excepto que los espacios se sustituyen por caracteres de guion bajo.

Tenga en cuenta que

* La etiqueta no puede ser una combinación de letras y números que se puedan confundir con una dirección de fila y columna. Por ejemplo, A100 no puede ser una etiqueta porque es la dirección de una celda de una hoja de cálculo.
* Los siguientes caracteres no son válidos en las etiquetas: `'#', '@', '!', '$', '^', '&', '&#42;', '` y `'~', ' '`. Se reemplazarán por caracteres de guion bajo.
* Cuando se introduce un nombre no válido, aparece un mensaje de advertencia que sugiere un nombre generado automáticamente. Si hace clic en **[!UICONTROL Sí]**, se usará este nombre. Si hace clic en **[!UICONTROL No]**, la interfaz de usuario del Asistente avanzado le permitirá escribir el nuevo nombre.
