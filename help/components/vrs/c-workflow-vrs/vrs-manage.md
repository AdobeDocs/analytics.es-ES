---
description: El Administrador de grupos de informes virtuales permite a los administradores editar, añadir, etiquetar, eliminar, cambiar el nombre, aprobar, copiar, exportar y filtrar grupos de informes virtuales. No es visible para los usuarios que no son administradores.
keywords: Grupo de informes virtuales
seo-description: El Administrador de grupos de informes virtuales permite a los administradores editar, añadir, etiquetar, eliminar, cambiar el nombre, aprobar, copiar, exportar y filtrar grupos de informes virtuales. No es visible para los usuarios que no son administradores.
seo-title: Administrar grupos de informes virtuales
solution: Analytics
title: Administrar grupos de informes virtuales
topic: Reports and Analytics
uuid: ce 683 c 01-2 d 7 d -4 f 2 a -98 db -946 f 68 eda 99 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Administrar grupos de informes virtuales

El Administrador de grupos de informes virtuales permite a los administradores editar, añadir, etiquetar, eliminar, cambiar el nombre, aprobar, copiar, exportar y filtrar grupos de informes virtuales. No es visible para los usuarios que no son administradores.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Componentes]** &gt; **[!UICONTROL Grupos de informes virtuales]**

![](assets/vrs-manage.png)

>[!NOTE]
>
>En el Administrador de grupos de informes virtuales solo puede ver sus propios grupos. Basta con hacer clic en **[!UICONTROL Mostrar todos]para ver los de otros usuarios.**

| Tarea | Descripción |
|--- |--- |
| Agregar | Le lleva al creador de grupos de informes virtuales, donde puede crear nuevos grupos de informes virtuales. |
| Etiqueta | Todos los usuarios pueden crear etiquetas para los segmentos y aplicar una o más a un segmento. Sin embargo, solo puede ver etiquetas de los segmentos de los que es propietario. ¿Qué tipo de etiquetas debería crear? A continuación encontrará una serie de sugerencias para crear etiquetas útiles:<ul><li>Etiquetas basadas en nombres de equipos, como Marketing social o Marketing móvil</li><li>Etiquetas de proyectos (etiquetas de análisis), como análisis de Páginas de entrada</li><li>Etiquetas de categorías: Para hombres o Área geográfica</li><li>Etiquetas de flujo de trabajo: Revisado para (unidad comercial específica); Aprobado</li></ul> |
| Eliminar | Si elimina un grupo de informes virtuales, los informes programados y los tableros que tenga aplicados este grupo seguirán funcionando normalmente. El informe o el tablero siguen usando el grupo de informes virtuales eliminado mientras no vuelva a guardar el informe programado.  Los informes programados no se actualizan cuando edita un grupo de informes virtuales con el mismo nombre.<br>Por ejemplo: Supongamos que tiene dos grupos de informes virtuales con el mismo nombre y distintos grupos de informes superiores:<br>Tiene un marcador que hace referencia al grupo de informes virtuales para el grupo de informes mainprod. A continuación, elimina el grupo de informes virtuales porque es un duplicado. El marcador seguirá funcionando y haciendo referencia a la definición del VRS eliminado. Si cambia la definición del resto del VRS, el VRS aplicado al marcador no cambia. Utiliza la definición antigua. Para arreglarlo, actualice el marcador a fin de que haga referencia a la definición nueva. Si no tiene la seguridad de que un marcador, tablero o informe programado esté utilizando un VRS eliminado, puede cambiar el nombre del resto del VRS para que quede claro que el marcador utiliza este resto. |
| Cambiar nombre | En cualquier sitio en el que aparece el grupo de informes virtuales, como el selector de grupos de informes, muestra el nuevo nombre. |
| Aprobar/Desaprobar | Aprobar los grupos de informes virtuales para hacerlos “oficiales” o “conforme a los cánones”. Puede invertir el proceso desaprobándolo. |
| Copiar | Crea una copia distinta con su nuevo ID del grupo de informes propio, pero con el mismo nombre y definición. |
| Exportar a CSV | Exporta la definición del grupo de informes virtuales a un archivo .csv. |
| Filtro | Filtra por etiquetas, grupo de informes superior, propietarios y otros (Mostrar todos, Míos, Favoritos y Aprobado). |
