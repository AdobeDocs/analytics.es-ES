---
description: Una utilidad de publicación es un contenedor que permite incrustar informes de marketing (marcadores y paneles) en una página web. Las personas de su organización que no tengan acceso a los informes de marketing pueden vista los datos pertinentes.
title: Widget de publicaciones
topic: Admin tools
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Widget de publicaciones

Una utilidad de publicación es un contenedor que permite incrustar informes de Analytics (marcadores y paneles) en una página web. Los miembros de la organización que no dispongan de acceso a los informes de Analytics también podrán ver los datos relevantes.

Por ejemplo, se puede disponer un tablero donde los ejecutivos de la empresa puedan ver el número de visitantes de la página, de visitantes de página únicos, etcétera.

>[!CAUTION] No se requiere autenticación para ver los datos publicados mediante la utilidad de publicación, por lo que se debe tener en cuenta que los datos publicados no son más seguros que los que se envían por correo electrónico a un servidor de listas o a un grupo de correo electrónico. Utilice la utilidad únicamente de conformidad con las normas de seguridad de su organización, los requisitos contractuales existentes y la legislación aplicable. La utilidad Publicación permite restringir, por dirección IP o ruta de dominio, el lugar donde se pueden publicar datos. Sin embargo, estos mecanismos están diseñados exclusivamente para evitar la distribución no deseada de datos y no son una manera eficaz de asegurar el acceso a los datos distribuidos a través de la utilidad de publicación.
>
> Adobe no asume ninguna responsabilidad ni obligación por los datos expuestos a través de la utilidad de publicación.

Dado que la utilidad Publicación puede generar grandes volúmenes de tráfico, Adobe se reserva el derecho, a su propia discreción, de desactivar las utilidades Publicación de una compañía por un uso incorrecto o un tráfico excesivo que repercuta en el rendimiento general.

## Resolución de problemas: caché de la utilidad de publicación

La utilidad ejecuta el informe la primera vez que un usuario ve la utilidad de publicación implementada. Una vez ejecutado el informe, los resultados se agregan a una caché y son válidos durante 1 hora. Cualquier usuario subsiguiente que vista la utilidad Publicación en la hora siguiente verá la versión en caché (regresará instantáneamente). Después de transcurrida una hora, cualquier usuario subsiguiente que vista la utilidad Publicación la obligará a ejecutar el informe de nuevo y, a continuación, estos resultados se almacenarán en caché, etc. De esa manera, se garantiza que los datos tengan como máximo una hora de antigüedad.

Si observa diferencias de datos entre la utilidad Publicación y la interfaz de sistema de informes, es posible que tenga que borrar la caché de la utilidad Publicación.

1. Haga clic en la utilidad Publicación (para que la utilidad esté seleccionada).
1. Click **[!UICONTROL Save]** on the widget.
1. Vuelva a ejecutar la utilidad. (El modo de Previsualización no utiliza la caché del widget.)

>[!NOTE] Los widgets de publicación solo muestran la primera columna de datos de un informe.

## Descripciones de los utilidades de publicación {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elemento | Descripción |
|--- |--- |
| Nombre | Nombre del widget. |
| Descripción | (Opcional) Especifique una descripción para la utilidad. |
| Información general de la tienda de aplicaciones | En la lista desplegable Informe superior, seleccione una carpeta o un panel. En la lista desplegable Informe inferior, seleccione un informe breve o un marcador.  Estos informes no requieren la autenticación de visitantes. <br>Si un visitante carga una página web que contiene una utilidad de publicación, la utilidad mostrará automáticamente el informe asociado utilizando los datos actuales de los informes. Si se cambia una utilidad de publicación, por ejemplo, si se cambia el informe asociado, se actualizará automáticamente el resultado del informe de todas las páginas web que utilicen esa utilidad, sin necesidad de volver a implementarlas.</br> |
| Destino | Permite especificar el destino de la utilidad   El destino debe tener un formato de dirección URL válido, con el prefijo https:// o https:// incluido. Los destinos de los utilidades de publicación son inclusivos, es decir, que el utilidad de publicación funcionará en todas las direcciones URL que incluyan el destino especificado. <br>Por ejemplo, un destino como https://www.corp1.com/sales/ permite que el widget de publicaciones aparezca en todas las páginas Web que se encuentren en el nivel de la página de ventas u otro nivel inferior dentro del sitio Web www.corp1.com.</br> |
