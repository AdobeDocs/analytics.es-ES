---
description: Métodos para optimizar el servicio de Report Builder y lista de mensajes de error que pueden producirse ocasionalmente.
title: Solución de problemas y prácticas recomendadas para Report Builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: Business Practitioner, Administrator
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '1401'
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

* **Empresa de inicio de sesión no válida**: Este error se produce normalmente si se escribe incorrectamente el nombre de la empresa de inicio de sesión o si hay problemas de actividad de red. Haga lo siguiente:
   * Revise el nombre de la compañía de inicio de sesión para asegurarse de que esté bien escrito y sin espacios innecesarios.
   * Inicie sesión en Analytics con la misma empresa de inicio de sesión para asegurarse de que sea correcta. Si no puede iniciar sesión con esas credenciales, póngase en contacto con los administradores de su organización para que le faciliten el nombre correcto de la empresa de inicio de sesión.
* **Cortafuegos**: Report Builder usa los puertos 80 y 443. Asegúrese de que estos puertos tienen permiso de paso en el cortafuegos de su empresa. Consulte también las direcciones IP internas de Adobe para conocer otras exclusiones de cortafuegos.

## Recomendaciones para optimizar solicitudes {#section_33EF919255BF46CD97105D8ACB43573F}

Los siguientes factores pueden aumentar la complejidad de la solicitud y dar como resultado un procesamiento más lento.

* **Factores que pueden ralentizar los envíos**: Se programaron demasiados marcadores, tableros y libros de Report Builder en un plazo de pocas horas. Se programaron demasiados libros de Report Builder con muy poca diferencia horaria. Si esto sucede, la cola API del informe se pone como pendiente.
* **Factores que ralentizan el tiempo de ejecución del libro**: Aumento significativo de las clasificaciones o aumento del intervalo de fechas de solicitud a lo largo del tiempo.
* **Causas que producen un error en la entrega del libro**: Fórmulas complejas de Excel, especialmente aquellas que implican fecha y hora.
* **Celdas que devuelven 0 (sin valores)**: La existencia de un apóstrofo o una comilla simple en el nombre de la hoja de Excel provocará que Report Builder no devuelva valores. (Se trata de una limitación de Microsoft Excel).
* **Rendimiento de solicitud individual**: La velocidad de procesamiento puede verse afectada por las siguientes configuraciones:

   | Configuración | Rendimiento más rápido | Rendimiento más lento |
   |--- |--- |--- |
   | Desgloses y el orden del desglose | Pocas | Muchas |
   |  | Ejemplo: si se desglosa de A a Z, el número de elementos para A debería ser siempre inferior al número de elementos para Z. Si es al contrario, el tiempo de solicitud puede aumentar significativamente. |
   | Intervalo de fechas | Intervalo pequeño | Intervalo grande |
   | Filtro | Filtro específico | Filtros más utilizados |
   | Granularidad | Agregado | Por hora<ul><li>Diario</li><li>Semanal</li><li>Mensual</li><li>Trimestral</li><li>Anual</li></ul> |
   | Número de entradas | Conjunto de datos pequeño | Conjunto de datos grande |

* **Horas de programación**: Escalonar la programación en un periodo de 24 horas (ver la siguiente tabla). Programar marcadores, tableros y libros de Report Builder existentes con muy poca diferencia horaria puede causar retrasos. Programar solicitudes más grandes y más complejas por la mañana temprano para permitir que las extracciones manuales y la actualización se produzcan a lo largo del día.

   | Hora de programación | 1 a. m. - 2 a. m. | 2 a. m. - 7 a. m. | 7 a. m. - 6 p. m. | 6 p. m. - Medianoche |
   |--- |--- |--- |--- |--- |
   | Uso de Report Builder | Tranquilo | Muy ocupado | Uso por lado del cliente.<br>Volúmenes más altos de usuarios que actualizan localmente y solicitan &quot;Enviar inmediatamente&quot;.<br>Además, se verifica si la cola de API está borrada cuando los libros programados vencen. | Desocupado |

* **Tiempos de espera**: Todos los informes programados tienen un tiempo de espera de cuatro horas. El sistema intenta programar tres veces más, pero posiblemente se producirá un fallo. (Generalmente, cuanto más grandes sean los conjuntos de datos más tardarán en ejecutarse). Esto puede comprobarse en los informes de [!DNL Analytics] y en Report Builder:

## Descripciones de los mensajes de error {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Lista de mensajes de error que se pueden producir ocasionalmente al utilizar Report Builder.

>[!NOTE]
>
>A continuación se incluye únicamente una selección de los mensajes de error y no una lista exhaustiva. Para obtener más información sobre la resolución de errores, póngase en contacto con su administrador.

* **Esta función solo se puede aplicar en un libro abierto.**: Este mensaje aparece si no hay libros (documentos de hoja de cálculo) abiertos en Excel y se hace clic en uno de los iconos de la barra de herramientas de Report Builder. Asimismo, la barra de herramientas se deshabilitará hasta que se abra una hoja de cálculo. Sin embargo, se puede hacer clic en el icono de ayuda en línea mientras la barra de herramientas esté activada sin que se produzca este error.
* **En primer lugar, debe salir del [!UICONTROL Asistente para solicitudes] antes activar el [!UICONTROL Administrador de solicitudes].**: A pesar de que el [!UICONTROL Administrador de solicitudes] y el [!UICONTROL Asistente para solicitudes] están vinculados funcionalmente, no es posible comenzar a trabajar con el [!UICONTROL administrador] antes de completar o cancelar las operaciones llevadas a cabo en el [!UICONTROL asistente].
* **No hay solicitudes asociadas a este rango.**: Este mensaje de error se produce si se hace clic en el botón [!UICONTROL Desde hoja] del [!UICONTROL Administrador de solicitudes] cuando una celda de la hoja de cálculo no contiene solicitudes. Para identificar qué celdas de la hoja de cálculo contienen solicitudes, haga clic en solicitudes individuales que estén incluidas en la tabla del [!UICONTROL Administrador de solicitudes]. Si una solicitud está asociada con celdas, las celdas aparecerán resaltadas cuando la solicitud se seleccione en la tabla.
* **El rango seleccionado no es válido. Seleccione otro rango.**: Si una celda de la hoja de cálculo se selecciona y ya tiene una solicitud asignada, se producirá este error. Elimine la solicitud asignada a las celdas o seleccione otro intervalo de celdas para asignar. Si desea eliminar celdas, es importante localizar las que contengan solicitudes y eliminar la solicitud antes de eliminar las celdas (eliminando filas o columnas).
* **Salga de la celda de Excel seleccionada antes de utilizar esta función.**: Si se encuentra en *modo de edición* en una celda de Excel y hace clic en uno de los iconos de Report Builder, se generará este mensaje de error. Estar en modo de edición en una celda de Excel significa que la celda está seleccionada y que el cursor aparece dentro de la celda. También se está en modo de edición en una celda de Excel cuando se escribe directamente en la barra de [!UICONTROL fórmulas] o en el [!UICONTROL cuadro de nombre] en la parte superior de Excel.
* **El rango seleccionado se cruza con el rango de otra solicitud. Cambie su selección.**: Este error aparecerá si ya ha asignado un conjunto de celdas a la hoja de cálculo.
* **Repara el libro (Registros eliminados: Fórmula de la parte /xl/calcChain.xml)**: A veces, las fórmulas de un libro se dañan al guardarse o transferirse. Cuando se abre el archivo, Excel intenta ejecutar estas fórmulas y falla. Para resolver este problema, elimine `calcChain.xml` de la hoja de cálculo y Excel actualizará los cálculos de la fórmula.
   1. Cambie el nombre de la extensión de archivo del libro de `.xlsx` a `.zip`.
   2. Descomprima el contenido y abra la carpeta `/xl/`.
   3. Eliminar `calcChain.xml`.
   4. Vuelva a comprimir el contenido y cambie la extensión de archivo a `.xlsx`.
   5. Abra el libro en Excel y actualice todas las solicitudes de Report Builder.
* **Las celdas de Excel asociadas con los filtros de entrada o el rango de salida pueden haberse eliminado**: Report Builder utiliza los nombres de Excel para adjuntar solicitudes de datos a las celdas. Si elimina los nombres de Excel del Administrador de nombres, verá este error. Las solicitudes no se pueden recuperar si se eliminan los nombres de Excel. Si el libro estaba programado, puede descargar una copia del Administrador de programación o abrir copias enviadas anteriormente del libro.
