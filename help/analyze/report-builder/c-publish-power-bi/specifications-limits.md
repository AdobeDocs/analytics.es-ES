---
description: Limitaciones al usar Report Builder y Microsoft Power BI.
title: Limitaciones y especificaciones
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 96%

---


# Limitaciones y especificaciones

## Restricciones de publicación de Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
> Estas restricciones se aplican únicamente a la opción “Publicar solicitudes de Report Builder como tablas de conjuntos de datos de Power BI”.

* Se puede exportar a Power BI un máximo de 100 solicitudes de Report Builder por cada libro.
* El proceso de programación detendrá las solicitudes de exportación al alcanzar la 101.ª solicitud.
* Solo las primeras 10 000 filas de datos de Analytics se enviarán a Power BI por cada solicitud de Report Builder. Las demás filas se ignorarán.

## Editar una solicitud de Report Builder después de publicar en Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
> Esta especificación se aplica a las opciones “Publicar todas las solicitudes de Report Builder como tablas de conjunto de datos de Power BI” y “Publicar todas las tablas con formato en el libro como tablas de conjuntos de datos de Power BI”.

Editar una solicitud de Report Builder tras su publicación en Power BI puede causar problemas.

* **Caso 1**: publica un libro en Power BI y crea una visualización basada en estos datos. A continuación, realiza cambios en el libro que provocan que desaparezca una de las columnas del conjunto de datos al que se hace referencia. Después, vuelve a publicar. Esto provocará un error de visualización en Power BI.

   **Este es un ejemplo de cómo se produce un error de visualización:**

   1. En Report Builder, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   2. Programe esta solicitud para que se publique en Power BI.
   3. En Power BI, cree una visualización para Página y Vistas de páginas.
   4. Ahora, edite el libro eliminando Vistas de páginas de la solicitud.
   5. Edite la programación del libro actualizado y vuelva a publicar la solicitud en Power BI.
   6. Una vez que el nuevo libro se envíe a Power BI

      1. Compruebe que se ha sobrescrito el conjunto de datos existentes, creado durante la primera publicación.
      2. Compruebe que la tabla page_1 está adecuadamente actualizada con las columnas Página y Visitas.
      3. Compruebe que hay errores en visualización, ya que hace referencia a la columna Vistas de página que ya no está presente en la tabla page_1.

   **Este es un ejemplo de cómo NO se produce un error de visualización**:

   1. En Report Builder, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   2. Programe esta solicitud para que se publique en Power BI.
   3. En Power BI, cree una visualización para Página y Vistas de páginas.
   4. Ahora, edite el libro en Report Builder agregando la métrica Visitas y conservando Página y Vistas de página.
   5. Edite la programación del libro actualizado y vuelva a publicar la solicitud en Power BI.
   6. Una vez que el nuevo libro se envíe a Power BI

      1. Compruebe que se ha sobrescrito el conjunto de datos existentes, creado durante la primera publicación.
      2. Compruebe que la tabla page_1 está adecuadamente actualizada con las columnas Página, Vistas de página y Visitas.
      3. Compruebe que la visualización sigue funcionando correctamente, ya que hace referencia a dos columnas que siguen presentes en la tabla page_1.


* **Caso 2**: ancla una sección de su libro a un tablero de Power BI y, más adelante, elimina del libro dicha sección (por ejemplo, un gráfico o una tabla). De este modo se produce un error de visualización.

## Cambiar el nombre de un informe de Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

De forma predeterminada, el nombre se rellena con el nombre de archivo del libro (sin la extensión .xlsx), aunque reemplazando los espacios con caracteres de guion bajo.

Tenga en cuenta que

* La etiqueta no puede ser una combinación de letras y números que pueda confundirse con una dirección de fila o columna. Por ejemplo, no puede haber una etiqueta A100 porque es una dirección de celda en un libro.
* Los siguientes caracteres no son válidos en las etiquetas: &quot;#&quot;, &quot;@&quot;, &quot;!&quot;, &quot;$&quot;, &quot;^&quot;, &quot;&amp;&quot;, &quot;*&quot;, &quot;`&quot;, &quot;~&quot;, &quot; &quot;. Se reemplazarán por caracteres de guion bajo.
* Si introduce un nombre no válido, aparece un mensaje de error que le sugiere un nombre generado automáticamente. Si hace clic en **[!UICONTROL Sí]**, se utilizará dicho nombre. Si hace clic en **[!UICONTROL No]**, la interfaz de usuario del Asistente avanzado le permitirá introducir uno nuevo.

