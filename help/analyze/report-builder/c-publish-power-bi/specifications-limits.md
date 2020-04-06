---
description: 'null'
title: Limitaciones y especificaciones
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Limitaciones y especificaciones

## Restricciones de publicación de Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE] Estas restricciones se aplican únicamente a la opción “Publicar solicitudes de Report Builder como tablas de conjuntos de datos de Power BI”.

* Se puede exportar a Power BI un máximo de 100 solicitudes de Report Builder por cada libro.
* El proceso de programación detendrá la exportación de solicitudes cuando se alcance la 101ª solicitud.
* Solo las primeras 10 000 filas de datos de Analytics se enviarán a Power BI por cada solicitud de Report Builder. Se omitirán las filas restantes.

## Editar una solicitud de Report Builder después de publicar en Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE] Esta especificación se aplica a las opciones “Publicar todas las solicitudes de Report Builder como tablas de conjunto de datos de Power BI” y “Publicar todas las tablas con formato en el libro como tablas de conjuntos de datos de Power BI”.

Editar una solicitud de Report Builder tras su publicación en Power BI puede causar problemas.

* **Caso 1**: Puede publicar un libro en Power BI y crear una visualización basada en sus datos. A continuación, se realizan cambios en el libro, lo que provoca que desaparezca una de las columnas del conjunto de datos al que hace referencia. A continuación, vuelva a publicar. Esto interrumpirá la visualización en Power BI.

   **A continuación se muestra un ejemplo de cómo se producirá un error en la visualización:**

   1. En Report Builder, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   1. [Programe la publicación de esta solicitud](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) en Power BI.
   1. En Power BI, cree una visualización para Vistas de página y página.
   1. Ahora edite el libro eliminando Vistas de página de la solicitud.
   1. Edite la programación con el libro actualizado y vuelva a publicar la solicitud en Power BI.
   1. Una vez enviado el nuevo libro a Power BI

      1. Compruebe que sobrescribió el conjunto de datos existente que se creó la primera vez que publicó.
      1. Compruebe que la tabla page_1 se actualiza correctamente con las columnas Página y Visitas.
      1. Compruebe que la visualización está dañada, ya que hace referencia a la columna Vistas de página que ya no está presente en la tabla page_1.
   **A continuación se muestra un ejemplo de cómo NO se producirá un error en la visualización:**

   1. En Report Builder, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   1. [Programe la publicación de esta solicitud](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) en Power BI.
   1. En Power BI, cree una visualización para Vistas de página y página.
   1. Ahora, edite el libro en Report Builder agregando la métrica Visitas y conservando Página y Vistas de página.
   1. Edite la programación con el libro actualizado y vuelva a publicar la solicitud en Power BI.
   1. Una vez enviado el nuevo libro a Power BI

      1. Compruebe que sobrescribió el conjunto de datos existente que se creó la primera vez que publicó.
      1. Compruebe que la tabla page_1 se actualiza correctamente con las columnas Página, Vistas de página y Visitas.
      1. Compruebe que la visualización sigue funcionando correctamente, ya que hace referencia a dos columnas que siguen presentes en la tabla page_1.


* **Caso 2**: Puede fijar una sección del libro en un panel de Power BI y, posteriormente, quitar esa sección fija (como un gráfico o una tabla) del libro. Esto interrumpirá la visualización.

## Cambiar el nombre de un informe de Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

De forma predeterminada, el nombre se rellenará con el nombre del archivo del libro (sin la extensión .xlsx), excepto que los espacios se reemplazarán con caracteres de subrayado.

Tenga en cuenta que

* La etiqueta no puede ser una combinación de letras y números que pueda confundirse con una dirección de fila y columna. Por ejemplo, A100 no puede ser una etiqueta porque es la dirección de una celda en una hoja de cálculo.
* Los siguientes caracteres no son caracteres de etiqueta válidos: &#39;#&#39;, &#39;@&#39;, &#39;!&#39;, &#39;$&#39;, &#39;^&#39;, &#39;&amp;&#39;, &#39;*&#39;, &#39;`&#39;, &#39;~&#39;, &#39; &#39; . Se reemplazarán por un carácter de subrayado.
* Cuando escriba un nombre no válido, se mostrará un mensaje de advertencia que sugerirá un nombre generado automáticamente. Si hace clic en **[!UICONTROL Yes]**, se utilizará este nombre. Si hace clic en **[!UICONTROL No]**, la IU del Asistente avanzado le permitirá introducir el nuevo nombre.

