---
description: Utilice la visualización de flujo en un proyecto de Workspace.
title: Configuración de una visualización de flujo
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
source-git-commit: ec466d2a503278b05d19eda09e2a2244897ce1f3
workflow-type: tm+mt
source-wordcount: '1417'
ht-degree: 100%

---

# Configuración de una visualización de flujo

Las visualizaciones de flujos le permiten comprender los recorridos que se derivan de un evento de conversión específico en el sitio web o la aplicación, o que conducen a él. Traza una ruta a través de las dimensiones (y elementos de dimensión) o las métricas. 

Las visualizaciones de flujos le permiten configurar el inicio o el final de la ruta que le interesa o analizar todas las rutas que fluyen a través de una dimensión o un elemento de dimensión.

![nueva interfaz de usuario de flujo](assets/new-flow.png)

## Crear una visualización de flujo {#configure}

1. Añada un panel en blanco al proyecto y haga clic en el icono de visualizaciones del carril izquierdo. 

   O

   Añada una visualización de cualquiera de las formas descritas en la sección “Añadir visualizaciones a un panel” de [Información general sobre visualizaciones](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Ancle la visualización de flujo mediante una de las opciones siguientes:

   * [!UICONTROL **Comienza con**] (métricas, dimensiones o elementos), o
   * [!UICONTROL **Contiene**] (dimensiones o elementos), o
   * [!UICONTROL **Finaliza con**] (métricas, dimensiones o elementos)

   Cada una de estas categorías se muestra como “zona de colocación”. Puede rellenar la zona de colocación de tres formas:

   * Utilice el menú desplegable para seleccionar métricas o dimensiones.
   * Arrastre las dimensiones o métricas en el carril izquierdo.
   * Empiece a escribir el nombre de una dimensión o métrica y, a continuación, selecciónela cuando aparezca en la lista desplegable.

   >[!IMPORTANT]
   >
   >Las métricas calculadas no se pueden usar con **[!UICONTROL Comienza con]** o **[!UICONTROL Finaliza con]**.

1. Si elige una métrica, también debe proporcionar una [!UICONTROL **Dimensión de rutas**] para usar como ruta de acceso o de salida del componente seleccionado, como se muestra aquí. El valor predeterminado es [!UICONTROL **Página**].

   ![dimensión de las rutas](assets/pathing-dim.png)

1. (Opcional) Seleccione **[!UICONTROL Mostrar configuración avanzada]** para configurar cualquiera de las siguientes opciones:

   ![configuración avanzada](assets/adv-settings.png)

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Etiquetas de ajustes]** | Normalmente, las etiquetas de los elementos de flujo se truncan para ahorrar espacio en la pantalla, pero puede hacer la etiqueta entera visible al marcar esta casilla.  Valor predeterminado = sin marcar. |
   | **[!UICONTROL Incluir instancias de repetición]** | Las visualizaciones de flujo se basan en instancias de una dimensión. Esta configuración le da la opción de incluir o excluir instancias repetidas, por ejemplo, recargas de página. Sin embargo, las repeticiones no se pueden eliminar de las visualizaciones de flujo que incluyen dimensiones multivalor, como listVars, listProps, s.product, eVars de comercialización, etc. <p>Esta opción está desactivada de forma predeterminada.</p> |
   | **[!UICONTROL Limitar a la primera/última ocurrencia]** | Limite las rutas a aquellas que comienzan/finalizan con la primera/última ocurrencia de una dimensión, un elemento o una métrica. Consulte la sección siguiente [Ejemplo de escenario para “limitar a la primera/última incidencia”](#example-scenario-for-limit-to-firstlast-occurrence) para obtener una explicación más detallada. |
   | **[!UICONTROL Número de columnas]** | El número de columnas que quiere incluir en el diagrama de flujo. Puede especificar hasta un máximo de 5 columnas. |
   | **[!UICONTROL Elementos expandidos por columna]** | Cuántos elementos desea incluir en cada columna. Puede especificar un máximo de 10 elementos expandidos por columna. |
   | **[!UICONTROL Contenedor de flujo]** | <ul><li>Visita</li><li>Visitante.</li></ul> Permite alternar entre visitas y visitantes para analizar las rutas seguidas por los visitantes. Estos ajustes le permiten comprender el compromiso del visitante a nivel de visitante (a lo largo de visitas) o restringir el análisis a una única visita. |

   >[!IMPORTANT]
   >
   >La combinación de **[!UICONTROL Número de columnas]** y **[!UICONTROL Elementos expandidos por columna]** determina el número de solicitudes subyacentes necesarias para crear la visualización del flujo. Cuanto más altos sean esos números, más tiempo se tarda en procesar una visualización.

1. Seleccione **[!UICONTROL Generar]**.

>[!INFO]
>
>**Ejemplo:** suponga que desea rastrear la ruta que siguieron los usuarios tanto hacia como desde las páginas más populares de su sitio.
>
>Para ello, haría lo siguiente:
> 
>1. Empiece a crear una visualización de flujo tal como se ha descrito anteriormente.
>1. Arrastre la dimensión [!UICONTROL **Página**] al campo **[!UICONTROL Contiene]** y, a continuación, seleccione [!UICONTROL **Generar**].
>1. La visualización de flujo se genera con la página más vista visible en el nodo de enfoque en el centro de la visualización. También verá las páginas principales que llevan a esa página (a la izquierda del nodo de enfoque), así como las páginas principales que salen de esa página de enfoque (a la derecha del nodo de enfoque).
>1. Analice los datos en el flujo, tal como se describe en [Ver y cambiar la salida del flujo](#view-and-change-the-flow-output).


## Ver y cambiar la salida del flujo {#output}

![salida del flujo](assets/flow-output.png)

En la parte superior del diagrama aparece un resumen de la configuración de flujo. El grosor de un trazado en el diagrama es proporcional a su actividad y los trazados con más actividad parecen más gruesos que los que tienen menos actividad.

Para explorar en profundidad los datos, tiene varias opciones:

* El diagrama de flujo es interactivo. Pase el ratón por encima del diagrama para cambiar los detalles que se muestran.

* Al seleccionar en un nodo del diagrama, aparecen los detalles de dicho nodo. Seleccione de nuevo el nodo para contraerlo.

  ![detalles del nodo](assets/node-details.png)

* Puede filtrar una columna para mostrar solo ciertos resultados, como incluir y excluir, especificar criterios, etc.

* Seleccione el signo más (+) de la izquierda para expandir una columna.

* Utilice las opciones del botón derecho que se explican a continuación para personalizar aún más la salida.

* Seleccione el icono de lápiz situado junto al resumen de la configuración para editar el flujo o volver a crearlo con diferentes opciones.

* También puede exportar y seguir analizando el diagrama de flujo como parte del archivo .CSV de un proyecto. Para ello, vaya a **[!UICONTROL Proyecto]** > **[!UICONTROL Descargar CSV]**.

## Filtro

Por encima de cada columna aparece un filtro cuando pasa el ratón por encima. Al hacer clic en el filtro, obtiene el mismo cuadro de diálogo de filtro que existe en la tabla de forma libre de hoy. Este filtro funciona igual que en la tabla de forma libre.

* Utilice la configuración avanzada para incluir o excluir determinados criterios con nuestra lista de operadores.
* Una vez que haya filtrado un elemento de la lista, esa columna específica reflejará el filtrado. (El filtro lo reduce para mostrar solo el elemento permitido en el filtro o elimina todos los elementos excepto el elemento que desee en el filtro.
* Todas las columnas descendentes y ascendentes deben persistir, siempre y cuando haya datos que fluyen a los nodos restantes.
* Una vez aplicado, el icono de filtro aparece en azul encima de la columna que está filtrando.
* Para quitar un filtro, seleccione el icono de filtro para abrir el menú de filtro. Quite los filtros aplicados y, a continuación, seleccione **[!UICONTROL Guardar]**. El flujo volverá a su estado anterior sin filtrar.

## Opciones con el botón derecho del ratón {#right-click}

| Opción | Descripción |
|--- |--- |
| [!UICONTROL Volver a empezar] | Le hace regresar al generador de diagramas improvisados, donde puede crear un nuevo diagrama de flujo. |
| [!UICONTROL Crear segmento para esta ruta] | Creación de segmentos. Esto le lleva al Generador de segmentos, donde puede configurar el nuevo segmento. |
| [!UICONTROL Desglose] | Desglosa el nodo mediante las dimensiones, métricas o tiempo disponibles. |
| [!UICONTROL Tendencia] | Crea un diagrama de tendencia para el nodo. |
| Mostrar columna siguiente / Mostrar columna anterior | Muestra la columna siguiente (derecha) o anterior (izquierda) de la visualización. |
| Ocultar columna | Oculta la columna seleccionada de la visualización. |
| [!UICONTROL Expandir toda la columna] | Expande una columna para mostrar todos los nodos. De forma predeterminada, únicamente se muestran los cinco nodos principales. |

## Ejemplo de escenario para «limitar a la primera/última incidencia»

Al utilizar esta opción, tenga en cuenta que:

* **[!UICONTROL Limitar a primera/última incidencia]** solo cuenta la primera/última incidencia de la serie. Todas las demás ocurrencias de los criterios **[!UICONTROL Comienza con]** o **[!UICONTROL Finaliza con]** se descartan.
* Si se usa con un flujo de **[!UICONTROL Comienza con]**, solo se incluye la primera incidencia que coincida con los criterios de inicio.
* Si se usa con un flujo de **[!UICONTROL Finaliza con]**, solo se incluirá la última incidencia que coincida con los criterios finales.
* La serie utilizada difiere según el contenedor. Si se usa el contenedor **[!UICONTROL Visita]**, la serie de visitas será la sesión. Si se usa el contenedor **[!UICONTROL Visitante]**, la serie de visitas será todas las visitas de un usuario determinado en el intervalo de fechas proporcionado.
* La opción **[!UICONTROL Limitar a primera/última incidencia]** se puede configurar en la configuración avanzada cuando se utiliza un elemento de Métrica o Dimensión en los campos «Comienza con» o «Finaliza con».

Ejemplo de serie de visitas:

Inicio > Productos > Agregar al carro > Productos > Agregar al carro > Facturación > Confirmación del pedido

### Considere un análisis de flujo con la siguiente configuración:

* Comience por[!UICONTROL  Agregar al carro] (Artículo Dimension)
* [!UICONTROL Página] dimensión de las rutas
* Contenedor de [!UICONTROL visita]

Si **[!UICONTROL Limitar a primera/última ocurrencia]** está *deshabilitado*, esta única serie de visitas contaría 2 ocurrencias de «Agregar al carro de compras».
Salida de flujo esperada:
«Agregar al carro de compras» (2) —> «Productos» (1)
-> «Facturación» (1)

Sin embargo, si **[!UICONTROL «Limitar a la primera/última ocurrencia»]** está *habilitado*, solo se incluirá en el análisis la primera ocurrencia de «Agregar al carro de compras».
Salida de flujo esperada:
«Agregar al carro de compras» (1) —> «Productos» (1)

### Considere la misma serie de visitas pero utilice la siguiente configuración:

* Finaliza con [!UICONTROL Agregar al carrito] (Artículo Dimension)
* [!UICONTROL Página] dimensión de las rutas
* Contenedor de [!UICONTROL visita]

Si **[!UICONTROL Limitar a primera/última ocurrencia]** está *deshabilitado*, esta única serie de visitas contaría 2 ocurrencias de «Agregar al carro de compras».
Salida de flujo esperada:
«Productos» (2) &lt;— «Agregar al carro de compras» (2)

Sin embargo, si **[!UICONTROL Limitar a primera/última ocurrencia]** está *habilitado*, solo la última ocurrencia de [!UICONTROL Agregar al carro de compras] se incluiría en el análisis.
Salida de flujo esperada:
«Productos» (1) &lt;— «Agregar al carro de compras» (1)
