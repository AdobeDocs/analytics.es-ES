---
description: 'null'
seo-description: 'null'
seo-title: Limitaciones y especificaciones
title: Limitaciones y especificaciones
uuid: 6717 b 6 ea -7 e 01-49 b 8-8 f 6 e-fb 733 a 03 b 687
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Limitaciones y especificaciones

## Power BI publishing restrictions {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Estas restricciones se aplican únicamente a la opción "Publicar solicitudes del Creador de informes como tablas de conjuntos de datos de Power BI".

* Se puede exportar a Power BI un máximo de 100 solicitudes del Creador de informes por cada libro.
* El proceso de programación detendrá las solicitudes de exportación al alcanzar la 101.ª solicitud.
* Solo las primeras 10 000 filas de datos de Analytics se enviarán a Power BI por cada solicitud del Creador de informes. Las demás filas se ignorarán.

## Edit a Report Builder request after publishing to Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Esta especificación se aplica a las opciones "Publicar todas las solicitudes del Creador de informes como tablas de conjuntos de datos de Power BI" y "Publicar todas las tablas con formato en el libro como tablas de conjuntos de datos de Power BI".

Editar una solicitud del Creador de informes tras su publicación en Power BI puede causar problemas.

* **Caso 1**: publica un libro en Power BI y crea una visualización basada en estos datos. A continuación, realiza cambios en el libro que provocan que desaparezca una de las columnas del conjunto de datos al que se hace referencia. Después, vuelve a publicar. Esto provocará un error de visualización en Power BI.

   **Este es un ejemplo de cómo se produce un error de visualización:**

   1. En el Creador de informes, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   1. [Programe esta solicitud](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) para que se publique en Power BI.
   1. En Power BI, cree una visualización para Página y Vistas de páginas.
   1. Ahora, edite el libro eliminando Vistas de páginas de la solicitud.
   1. Edite la programación del libro actualizado y vuelva a publicar la solicitud en Power BI.
   1. Una vez que el nuevo libro se envíe a Power BI

      1. Compruebe que se ha sobrescrito el conjunto de datos existentes, creado durante la primera publicación.
      1. Compruebe que la tabla page_1 está adecuadamente actualizada con las columnas Página y Visitas.
      1. Compruebe que hay errores en visualización, ya que hace referencia a la columna Vistas de página que ya no está presente en la tabla page_1.
   **Este es un ejemplo de cómo NO se produce un error de visualización**:

   1. En el Creador de informes, cree un libro con una solicitud, empleando para ello la dimensión Página y la métrica Vistas de página.
   1. [Programe esta solicitud](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) para que se publique en Power BI.
   1. En Power BI, cree una visualización para Página y Vistas de páginas.
   1. Ahora, edite el libro en el Creador de informes agregando la métrica Visitas y conservando Página y Vistas de página.
   1. Edite la programación del libro actualizado y vuelva a publicar la solicitud en Power BI.
   1. Una vez que el nuevo libro se envíe a Power BI

      1. Compruebe que se ha sobrescrito el conjunto de datos existentes, creado durante la primera publicación.
      1. Compruebe que la tabla page_1 está adecuadamente actualizada con las columnas Página, Vistas de página y Visitas.
      1. Compruebe que la visualización sigue funcionando correctamente, ya que hace referencia a dos columnas que siguen presentes en la tabla page_1.


* **Caso 2**: ancla una sección de su libro a un tablero de Power BI y, más adelante, elimina del libro dicha sección (por ejemplo, un gráfico o una tabla). De este modo se produce un error de visualización.

## Change the name of a Power BI report {#section_2E7893A78B914EBFACB2B08CBD9E472E}

De forma predeterminada, el nombre se rellena con el nombre de archivo del libro (sin la extensión .xlsx), aunque reemplazando los espacios con caracteres de guion bajo.

Tenga en cuenta que

* La etiqueta no puede ser una combinación de letras y números que pueda confundirse con una dirección de fila o columna. Por ejemplo, no puede haber una etiqueta A100 porque es una dirección de celda en un libro.
* Los siguientes caracteres no son válidos en las etiquetas: "#", "@", "!", "$", "^", "&amp;", "*", "`", "~", " ". Se reemplazarán por caracteres de guion bajo.
* Si introduce un nombre no válido, aparece un mensaje de error que le sugiere un nombre generado automáticamente. If you click **[!UICONTROL Yes]**, this name will be used. If you click **[!UICONTROL No]**, the Advanced Wizard UI will let you enter the new name.

