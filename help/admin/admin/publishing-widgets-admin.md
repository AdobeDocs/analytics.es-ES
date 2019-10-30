---
description: Una utilidad de publicación es un contenedor que permite incrustar informes de marketing (marcadores y tableros) en una página web. Los miembros de la organización que no dispongan de acceso a los informes de marketing también podrán ver los datos relevantes.
seo-description: Una utilidad de publicación es un contenedor que permite incrustar informes de marketing (marcadores y tableros) en una página web. Los miembros de la organización que no dispongan de acceso a los informes de marketing también podrán ver los datos relevantes.
seo-title: Widget de publicaciones
solution: Analytics
title: Widget de publicaciones
topic: Herramientas de administración
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# Widget de publicaciones

Una utilidad de publicación es un contenedor que permite incrustar informes de Analytics (marcadores y tableros) en una página web. Las personas de su organización que no tengan acceso a los informes de Analytics pueden ver los datos pertinentes.

Por ejemplo, se puede disponer un tablero donde los ejecutivos de la empresa puedan ver el número de visitantes de la página, de visitantes de página únicos, etcétera.

> [!CAUTION] No se requiere autenticación para ver los datos publicados mediante la utilidad de publicación, por lo que se debe tener en cuenta que los datos publicados no son más seguros que los que se envían por correo electrónico a un servidor de listas o a un grupo de correo electrónico. La utilidad solo se debe utilizar de conformidad con la legislación aplicable, los requisitos contractuales existentes y los estándares de seguridad de la organización. La utilidad de publicación permite restringir la ubicación de publicación de los datos por dirección IP o ruta de dominio. No obstante, estos mecanismos se han diseñado exclusivamente para evitar la distribución no deseada de datos y no protegen de un modo eficaz el acceso a los datos distribuidos mediante la utilidad de publicación.
>
> Adobe no asume ninguna responsabilidad ni obligación por los datos expuestos a través de la utilidad de publicación.

Dado que las utilidades Publicación tienen el potencial de generar altos volúmenes de tráfico, Adobe se reserva el derecho, a su propia discreción, de desactivar las utilidades Publicación de la empresa debido al uso inapropiado o al tráfico excesivo que repercuta en el rendimiento en general.

## Resolución de problemas: caché de la utilidad de publicación

La utilidad ejecuta el informe la primera vez que cualquier usuario ve la utilidad de publicación implementado. Tras la ejecución del informe, se agregan los resultados a una memoria caché y son válidos durante 1 hora. Cualquier usuario subsiguiente que vea la utilidad de publicación en la hora siguiente verá la versión almacenada en caché (regresará instantáneamente). Transcurrida una hora, cualquier usuario subsiguiente que vea el widget de publicación forzará la utilidad a ejecutar el informe nuevamente, luego los resultados se almacenarán en la memoria caché, y así sucesivamente. De esa forma, se garantiza que los datos no tengan más de una hora.

Si ve diferencias entre los datos de la utilidad de publicación y la interfaz de informes, es posible que tenga que borrar el contenido de la caché de la utilidad de publicación.

1. Haga clic en la utilidad de publicación (de modo que el foco se sitúe sobre la utilidad).
1. Haga clic en **[!UICONTROL Guardar]en la utilidad.**
1. Vuelva a ejecutar la utilidad. (El modo de Vista previa no usa la caché de la utilidad).

> [!NOTE] Las utilidades de publicación solo muestran la primera columna de datos de un informe.

## Descripciones de los utilidades de publicación {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elemento | Descripción |
|--- |--- |
| Nombre | El nombre de la utilidad. |
| Descripción | Opcional. Permite escribir una descripción de la utilidad. |
| Número de visita | En la lista desplegable Informe superior, seleccione una carpeta o un tablero. En la lista desplegable Informe inferior, seleccione un informe breve o un marcador.  Estos informes no requieren la autenticación de visitantes. <br>Si un visitante carga una página web que contiene una utilidad de publicación, la utilidad mostrará automáticamente el informe asociado utilizando los datos actuales de los informes. Si se cambia una utilidad de publicación, por ejemplo, si se cambia el informe asociado, se actualizará automáticamente el resultado del informe de todas las páginas web que utilicen esa utilidad, sin necesidad de volver a implementarlas.</br> |
| Destino | Permite especificar el destino de la utilidad   Los destinos deben tener un formato de URL válido, incluido el prefijo https:// o https://. Los destinos de los utilidades de publicación son inclusivos, es decir, que el utilidad de publicación funcionará en todas las direcciones URL que incluyan el destino especificado. <br>Por ejemplo, un Destino de https://www.corp1.com/sales/ permite las utilidades Publicación en todas las páginas Web en la página de ventas o debajo de ella en el sitio Web www.corp1.com.</br> |