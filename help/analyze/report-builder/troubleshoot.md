---
description: Métodos para optimizar el servicio de Report Builder y lista de mensajes de error que pueden producirse ocasionalmente.
title: Solución de problemas y prácticas recomendadas para Report Builder
topic: Report builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '1371'
ht-degree: 100%

---


# Solución de problemas y prácticas recomendadas para Report Builder

Métodos para optimizar el servicio de Report Builder y lista de mensajes de error que pueden producirse ocasionalmente.

## Usuarios de Report Builder 5.0 y abrir libros de trabajo de la versión 5.1 {#section_C29898775999453FABB5FB0E098415C8}

Adobe ha cambiado el separador entre dimensiones y clasificaciones de un carácter de guión bajo (_) a ||. Este cambio tiene implicaciones de compatibilidad para un usuario de Report Builder 5.0 que abra un libro de Report Builder v5.1 con solicitudes de clasificación. Cada vez que se abre un libro de una versión anterior a la v5.1, todas sus solicitudes de clasificaciones serializadas se convertirán a este formato.

Esto presenta un problema de compatibilidad avanzada: una vez actualice a la versión 5.1, si un libro se comparte con un usuario de Report Builder 5.0, ese usuario no podrá reconocer la solicitud de clasificación. De hecho, buscará “_” pero la versión 5.1 habrá serializado “||”.

Experimentará el siguiente efecto secundario al abrir un libro ARB v5.1 con solicitud de clasificación:

* Al abrir el libro, aparecerá la siguiente advertencia: “Este libro se guardó por última vez utilizando Report Builder 5.1. Esta versión ha introducido algunas funciones que son incompatibles con la versión de Report Builder instalada en este equipo. Se recomienda que actualice Report Builder a la última versión antes de actualizar este libro”.
* Si hace clic con el botón secundario en una solicitud ARB con clasificación, no se mostrarán los menús contextuales de Report Builder (editar solicitud, agregar solicitud dependiente...).
* Si ejecuta Actualizar todo, haciendo clic en el tercer botón o actualizando un grupo de solicitudes desde el formulario del Administrador de solicitudes, la solicitud de clasificación se ejecutará sin errores. No obstante, no se escribirán los valores de clasificación.
* Aún puede editar la solicitud abriendo el Administrador de solicitudes; a continuación, avance fila a fila hasta que alcance la solicitud correcta.
* Si edita la solicitud, deja todos los parámetros como están y, a continuación, hace clic en Finalizar, la respuesta se escribirá correctamente. De hecho, editar la solicitud resuelve el problema ya que los parámetros de Diseño de respuesta se reserializan. Por tanto, existe una solución aunque requiere tiempo.

## Problemas de autenticación en Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder requiere autenticación para crear solicitudes de datos a partir de grupos de informes. A veces se producen problemas al iniciar sesión en Report Builder, los cuales pueden variar según la configuración de [!DNL Analytics] o de la red.

**Empresa de inicio de sesión no válida**

Este error se produce normalmente si se escribe incorrectamente el nombre de la empresa de inicio de sesión o si hay problemas de actividad de red. Haga lo siguiente:

* Revise el nombre de la compañía de inicio de sesión para asegurarse de que esté bien escrito y sin espacios innecesarios.
* Inicie sesión en Analytics con la misma empresa de inicio de sesión para asegurarse de que sea correcta. Si no puede iniciar sesión con esas credenciales, póngase en contacto con los administradores de su organización para que le faciliten el nombre correcto de la empresa de inicio de sesión.

**Cortafuegos**

Report Builder usa los puertos 80 y 443. Asegúrese de que estos puertos tienen permiso de paso en el cortafuegos de su empresa. Consulte también las direcciones IP internas de Adobe para conocer otras exclusiones de cortafuegos.

## Recomendaciones para optimizar solicitudes {#section_33EF919255BF46CD97105D8ACB43573F}

Los siguientes factores pueden aumentar la complejidad de la solicitud y dar como resultado un procesamiento más lento:

**Factores que pueden ralentizar los envíos**

* Se programaron demasiados marcadores, tableros y libros de Report Builder en un plazo de pocas horas.
* Se programaron demasiados libros de Report Builder con muy poca diferencia horaria. Si esto sucede, la cola API del informe se pone como pendiente.

**Factores que ralentizan el tiempo de ejecución del libro**

* Aumento significativo de las clasificaciones.
* Aumento con el paso del tiempo del intervalo de fechas de solicitud.

   **Ejemplo**: imagine que crea una solicitud de tendencias utilizando la configuración Año actual, desglosado por la granularidad de Día. A finales de año, la solicitud devolverá más periodos que el creado a principios de año.

   `(January 1 - January 30 versus January 1 - December 31.)`

**Causas que producen un fallo del envío del libro**

Fórmulas complejas de Excel, especialmente aquellas que implican fecha y hora.

**Celdas que devuelven 0 (sin valor)**

La existencia de un apóstrofo o una comilla simple en el nombre de la hoja de Excel provocará que Report Builder no devuelva valores. (Se trata de una limitación de Microsoft Excel).

**Rendimiento de solicitud individual**

La velocidad de procesamiento puede verse afectada por las siguientes configuraciones:

| Configuración | Rendimiento más rápido | Rendimiento más lento |
|--- |--- |--- |
| Desgloses y el orden del desglose | Pocas | Muchas |
|  | Ejemplo: si se desglosa de A a Z, el número de elementos para A debería ser siempre inferior al número de elementos para Z. Si es al contrario, el tiempo de solicitud puede aumentar significativamente. |
| Intervalo de fechas | Intervalo pequeño | Intervalo grande |
| Filtro | Filtro específico | Filtros más utilizados |
| Granularidad | Agregado | Por hora<ul><li>Diario</li><li>Semanal</li><li>Mensual</li><li>Trimestral</li><li>Anual</li></ul> |
| Número de entradas | Conjunto de datos pequeño | Conjunto de datos grande |


**Horas de programación**

Escalonar la programación en un periodo de 24 horas (ver la siguiente tabla). Programar marcadores, tableros y libros de Report Builder existentes con muy poca diferencia horaria puede causar retrasos.

Programar solicitudes más grandes y más complejas por la mañana temprano para permitir que las extracciones manuales y la actualización se produzcan a lo largo del día.

| Hora de programación | 1 a. m. - 2 a. m. | 2 a. m. - 7 a. m. | 7 a. m. - 6 p. m. | 6 p. m. - Medianoche |
|--- |--- |--- |--- |--- |
| Uso de Report Builder | Tranquilo | Muy ocupado | Uso por lado del cliente.<br>Volúmenes más altos de usuarios que actualizan localmente y solicitan &quot;Enviar inmediatamente&quot;.<br>Además, se verifica si la cola de API está borrada cuando los libros programados vencen. | Desocupado |

**Tiempos de espera**

Todos los informes programados tienen un tiempo de espera de cuatro horas. El sistema intenta programar tres veces más, pero posiblemente se producirá un fallo. (Generalmente, cuanto más grandes sean los conjuntos de datos más tardarán en ejecutarse). Esto puede comprobarse en los informes de [!DNL Analytics] y en Report Builder:

* [!DNL Analytics]: **[!UICONTROL Favoritos]** > **[!UICONTROL Informes programados]**

* Report Builder: haga clic en **[!UICONTROL Administración]**, en la ficha [!UICONTROL Complementos] de Excel.

## Descripciones de los mensajes de error {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Lista de mensajes de error que se pueden producir ocasionalmente al utilizar Report Builder.

>[!NOTE]
>
>A continuación se incluye únicamente una selección de los mensajes de error y no una lista exhaustiva. Para obtener más información sobre la resolución de errores, póngase en contacto con su administrador.

**Esta función solo se puede aplicar en un libro abierto.**

Este mensaje aparece si no hay libros (documentos de hoja de cálculo) abiertos en Excel y se hace clic en uno de los iconos de la barra de herramientas de Report Builder. Asimismo, la barra de herramientas se deshabilitará hasta que se abra una hoja de cálculo. Sin embargo, se puede hacer clic en el icono de ayuda en línea mientras la barra de herramientas esté activada sin que se produzca este error.

**En primer lugar, debe salir del[!UICONTROL Asistente para solicitudes]antes activar el[!UICONTROL Administrador de solicitudes].**

A pesar de que el [!UICONTROL Administrador de solicitudes] y el [!UICONTROL Asistente para solicitudes] están vinculados funcionalmente, no es posible comenzar a trabajar con el [!UICONTROL administrador] antes de completar o cancelar las operaciones llevadas a cabo en el [!UICONTROL asistente].

**No hay solicitudes asociadas a este rango.**

Este mensaje de error se produce si se hace clic en el botón [!UICONTROL Desde hoja] del [!UICONTROL Administrador de solicitudes] cuando una celda de la hoja de cálculo no contiene solicitudes.

Para identificar qué celdas de la hoja de cálculo contienen solicitudes, haga clic en solicitudes individuales que estén incluidas en la tabla del [!UICONTROL Administrador de solicitudes]. Si una solicitud está asociada con celdas, las celdas aparecerán resaltadas cuando la solicitud se seleccione en la tabla.

**El rango seleccionado no es válido. Seleccione otro rango.**

Si una celda de la hoja de cálculo se selecciona y ya tiene una solicitud asignada, se producirá este error. Elimine la solicitud asignada a las celdas o seleccione otro intervalo de celdas para asignar.

Si desea eliminar celdas, es importante localizar las que contengan solicitudes y eliminar la solicitud antes de eliminar las celdas (eliminando filas o columnas).

**Salga de la celda de Excel seleccionada antes de utilizar esta función.**

Si se encuentra en *modo de edición* en una celda de Excel y hace clic en uno de los iconos de Report Builder, se generará este mensaje de error. Estar en modo de edición en una celda de Excel significa que la celda está seleccionada y que el cursor aparece dentro de la celda. También se está en modo de edición en una celda de Excel cuando se escribe directamente en la barra de [!UICONTROL fórmulas] o en el [!UICONTROL cuadro de nombre] en la parte superior de Excel.

**El rango seleccionado se cruza con el rango de otra solicitud. Cambie su selección.**

Este error aparecerá si ya ha asignado un conjunto de celdas a la hoja de cálculo.

Un modo de determinar qué celdas están asignadas antes de añadir nuevas solicitudes, consiste en cerrar el [!UICONTROL Asistente para solicitudes] y abrir el [!UICONTROL Administrador de solicitudes]. A continuación, seleccione uno a uno los elementos incluidos en la tabla de resumen de la solicitud. Siempre que seleccione una solicitud de la lista, las celdas que contengan asignaciones de la solicitud en la hoja de cálculo se resaltarán.

Este es un motivo por el que se debe considerar la posibilidad de marcar las celdas con resaltado, información de columna o fila o un estilo de formato antes de asignar varias celdas a diversas áreas.
