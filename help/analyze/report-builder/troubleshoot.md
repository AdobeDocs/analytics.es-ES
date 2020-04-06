---
description: Métodos para optimizar el servicio de Report Builder y lista de mensajes de error que pueden producirse ocasionalmente.
title: Solución de problemas y prácticas recomendadas para Report Builder
topic: Report builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Solución de problemas y prácticas recomendadas para Report Builder

Métodos para optimizar el servicio de Report Builder y lista de mensajes de error que pueden producirse ocasionalmente.

## Usuarios de Report Builder 5.0 y abrir libros de trabajo de la versión 5.1 {#section_C29898775999453FABB5FB0E098415C8}

Adobe ha cambiado el separador entre dimensiones y clasificaciones de un carácter de guión bajo (_) a ||. Este cambio tiene implicaciones de compatibilidad para un usuario de Report Builder 5.0 que abra un libro de Report Builder v5.1 con solicitudes de clasificación. Cada vez que se abre un libro de una versión anterior a la v5.1, todas sus solicitudes de clasificación serializadas se convierten a este formato.

Esto presenta un problema de compatibilidad avanzada: una vez actualice a la versión 5.1, si un libro se comparte con un usuario de Report Builder 5.0, ese usuario no podrá reconocer la solicitud de clasificación. De hecho, buscará “_” pero la versión 5.1 habrá serializado “||”.

Experimentará el siguiente efecto secundario al abrir un libro ARB v5.1 con solicitud de clasificación:

* Al abrir el libro, aparecerá la siguiente advertencia: “Este libro se guardó por última vez utilizando Report Builder 5.1. Esta versión ha introducido algunas funciones que son incompatibles con la versión de Report Builder instalada en este equipo. Se recomienda que actualice Report Builder a la última versión antes de actualizar este libro”.
* Si hace clic con el botón secundario en una solicitud ARB con clasificación, no se mostrarán los menús contextuales de Report Builder (editar solicitud, agregar solicitud dependiente...).
* Si ejecuta Actualizar todo, haciendo clic en el tercer botón o actualizando un grupo de solicitudes desde el formulario del Administrador de solicitudes, la solicitud de clasificación se ejecutará sin errores. Sin embargo, los valores de las clasificaciones no se escribirán.
* Aún puede editar la solicitud abriendo el Administrador de solicitudes y, a continuación, yendo de fila en fila, hasta que llegue a la solicitud correcta.
* Si edita la solicitud, deja todos los parámetros como están y, a continuación, hace clic en Finalizar, la respuesta se escribirá correctamente. De hecho, editar la solicitud resuelve el problema ya que los parámetros de Diseño de respuesta se reserializan. Así que hay una solución, aunque es lenta.

## Problemas de autenticación en Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder requiere autenticación para crear solicitudes de datos a partir de grupos de informes. A veces se producen problemas al iniciar sesión en Report Builder, los cuales pueden variar según la configuración de [!DNL Analytics] o de la red.

**Empresa de inicio de sesión no válida**

Este error suele producirse cuando la compañía de inicio de sesión no se ha introducido correctamente o cuando hay problemas de actividad de red. Haga lo siguiente:

* Compruebe la ortografía de la compañía de inicio de sesión para asegurarse de que no hay un error tipográfico o un espacio errante.
* Inicie sesión en Analytics con la misma empresa de inicio de sesión para asegurarse de que sea correcta. Si no puede iniciar sesión con esas credenciales, póngase en contacto con los administradores de su organización para que le faciliten el nombre correcto de la empresa de inicio de sesión.

**Cortafuegos**

Report Builder usa los puertos 80 y 443. Asegúrese de que estos puertos están permitidos a través del servidor de seguridad de su organización. Consulte también Direcciones IP internas de Adobe para obtener más exclusiones de cortafuegos.

## Recomendaciones para optimizar solicitudes {#section_33EF919255BF46CD97105D8ACB43573F}

Los siguientes factores pueden aumentar la complejidad de la solicitud y dar como resultado un procesamiento más lento:

**Factores que pueden ralentizar los envíos**

* Se programaron demasiados marcadores, tableros y libros de Report Builder en un plazo de pocas horas
* Se programaron demasiados libros de Report Builder con muy poca diferencia horaria. Si esto sucede, la cola API del informe se pone como pendiente.

**Factores que ralentizan el tiempo de ejecución del libro**

* Aumento significativo en las clasificaciones.
* Aumento del intervalo de fechas de la solicitud con el paso del tiempo.

   **Ejemplo**: imagine que crea una solicitud de tendencias utilizando la configuración Año actual, desglosado por la granularidad de Día. A finales de año, la solicitud devolverá más periodos que el creado a principios de año.

   `(January 1 - January 30 versus January 1 - December 31.)`

**Causas que producen un fallo del envío del libro**

Fórmulas complejas de Excel, especialmente aquellas que implican fecha y hora.

**Celdas que devuelven 0 (sin valor)**

La existencia de un apóstrofo o una comilla simple en el nombre de la hoja de Excel provocará que Report Builder no devuelva valores. (Esta es una limitación de Microsoft Excel).

**Rendimiento de solicitud individual**

La velocidad de procesamiento puede verse afectada por los siguientes ajustes:

| Configuración | Rendimiento más rápido | Rendimiento más lento |
|--- |--- |--- |
| Desgloses y orden de desglose | Pocas | Muchas |
|  | Ejemplo: si se desglosa de A a Z, el número de elementos para A debería ser siempre inferior al número de elementos para Z. Si es al contrario, el tiempo de solicitud puede aumentar significativamente. |
| Intervalo de fechas | Intervalo pequeño | Amplia gama |
| Filtro | Filtro específico | Filtros más utilizados |
| Granularidad | Agregado | Cada hora<ul><li>Cada día</li><li>Semanal</li><li>Mensual</li><li>Trimestral</li><li>Anual</li></ul> |
| Número de entradas | Conjunto de datos pequeño | Conjunto de datos grande |


**Horas de programación**

Escalonar la programación en un periodo de 24 horas (ver la siguiente tabla). Programar marcadores, tableros y libros de Report Builder existentes con muy poca diferencia horaria puede causar retrasos.

Programe solicitudes más grandes y complejas por la mañana temprano para permitir que se produzcan extracciones manuales y actualizaciones durante el día hábil.

| Tiempo de programación | 1 a.m. - 2 a.m. | 2 a.m. - 7 a.m. | 7 a.m. - 18.00 horas | 18.00 horas - Medianoche |
|--- |--- |--- |--- |--- |
| Uso de Report Builder | Tranquilo | Muy ocupado | Uso del cliente.<br>Volúmenes más altos de usuarios que actualizan localmente y solicitan &quot;Enviar inmediatamente&quot;.<br>Además, se verifica si la cola de API está borrada cuando los libros programados vencen. | No ocupado |

**Tiempos de espera**

Cualquier informe programado caduca pasados cuatro horas. El sistema intenta programar tres veces más, lo que puede resultar en un error. (Generalmente, cuanto más grandes sean los conjuntos de datos más tardarán en ejecutarse). Esto puede comprobarse en los informes de [!DNL Analytics] y en Report Builder:

* [!DNL Analytics]: **[!UICONTROL Favorites]** > **[!UICONTROL Scheduled Reports]**

* Report Builder: Click **[!UICONTROL Management]** in the [!UICONTROL Add-ins] tab in Excel.

## Descripciones de los mensajes de error {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Lista de mensajes de error que se pueden producir ocasionalmente al utilizar Report Builder.

>[!NOTE] A continuación se incluye únicamente una selección de los mensajes de error y no una lista exhaustiva. Para obtener más información sobre la resolución de errores, póngase en contacto con su administrador.

**Esta función solo se puede aplicar en un libro abierto.**

Este mensaje aparece si no hay libros (documentos de hoja de cálculo) abiertos en Excel y se hace clic en uno de los iconos de la barra de herramientas de Report Builder. Además, la barra de herramientas se desactiva hasta que se abre una hoja de cálculo. Sin embargo, puede hacer clic en el icono de ayuda en línea mientras la barra de herramientas sigue activada sin provocar este error.

**Primero debe salir del[!UICONTROL Request Wizard]antes de activar el[!UICONTROL Request Manager].**

Aunque los [!UICONTROL Request Manager] y los [!UICONTROL Request Wizard] están vinculados funcionalmente, no es posible trabajar con los [!UICONTROL Request Manager] antes de completar o cancelar las acciones realizadas en el [!UICONTROL Request Wizard].

**No hay solicitudes asociadas a este rango.**

Este mensaje de error se produce si hace clic en el [!UICONTROL From Sheet] botón de la [!UICONTROL Request Manager] hoja cuando una celda de la hoja de cálculo no contiene solicitudes.

Para identificar qué celdas de la hoja de cálculo contienen solicitudes, haga clic en las solicitudes individuales enumeradas en la tabla de la [!UICONTROL Request Manager]. Si una solicitud está asociada a celdas, las celdas aparecerán resaltadas cuando la solicitud esté seleccionada en la tabla.

**El rango seleccionado no es válido. Seleccione otro rango.**

Si se selecciona una celda de la hoja de cálculo y ya tiene una solicitud asignada a ella, se producirá este error. Elimine la solicitud asignada a las celdas o elija otro rango de celdas para asignar.

Cuando desee eliminar celdas, es importante localizar las que contengan solicitudes y eliminar la solicitud antes de eliminar las celdas (eliminando filas o columnas).

**Salga de la celda de Excel seleccionada antes de utilizar esta función.**

Si se encuentra en *modo de edición* en una celda de Excel y hace clic en uno de los iconos de Report Builder, se generará este mensaje de error. El modo de edición en una celda de Excel significa que la celda está seleccionada y que el cursor aparece dentro de la celda. También está en modo de edición en una celda de Excel cuando escribe directamente en la [!UICONTROL Formula] barra o en la [!UICONTROL Name Box] parte superior de Excel.

**El rango seleccionado se cruza con el rango de otra solicitud. Cambie su selección.**

Si ya ha asignado un conjunto de celdas a la hoja de cálculo, se muestra este error.

Una manera de determinar qué celdas se asignan antes de agregar nuevas solicitudes es cerrar el [!UICONTROL Request Wizard] y abrir el [!UICONTROL Request Manager]. A continuación, seleccione los elementos enumerados en la tabla de resumen de la solicitud uno por uno. Siempre que seleccione una solicitud en la lista, se resaltarán las celdas correspondientes que contengan asignaciones de solicitud en la hoja de cálculo.

Este es un motivo por el que debe considerar marcar las celdas con resaltado, información de columna o fila o un estilo de formato antes de asignar varias celdas a varias áreas.
