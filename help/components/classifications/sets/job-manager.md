---
title: Administrador de trabajos del conjunto de clasificaciones
description: Ver los trabajos de clasificación actuales y completados generados a partir de los conjuntos de clasificaciones.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: cc01d492dbbf99fc6a2736c4c50d889933d6f4ff
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---

# Administrador de trabajos de conjuntos de clasificaciones

El Administrador de trabajos de conjuntos de clasificaciones permite ver los trabajos de clasificación actuales y completados que se generaron a partir de conjuntos de clasificaciones. También puede utilizar esta interfaz para descargar datos de clasificación o plantillas para un trabajo en particular, o cargar datos adicionales en un trabajo.

>[!NOTE]
>
>Esta funcionalidad estará disponible para todos los clientes que tengan sus grupos de informes migrados a la nueva arquitectura de clasificaciones. Para obtener más información, póngase en contacto con el Servicio de atención al cliente de Adobe o con su Administrador de cuentas.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Trabajos]**

Tenga en cuenta que no puede crear trabajos desde esta interfaz. En su lugar, puede crear trabajos cargando datos en un conjunto de clasificaciones, solicitando un archivo de descarga o solicitando un archivo de plantilla.

## Filtrar conjuntos de clasificaciones

La parte izquierda del Administrador de trabajos de conjuntos de clasificaciones proporciona una configuración de filtro para localizar el trabajo deseado. Al hacer clic en el icono de filtro, se alterna la visibilidad de la configuración del filtro. Puede filtrar los conjuntos de clasificaciones por **[!UICONTROL Conjunto de clasificaciones]**, **[!UICONTROL Hora de finalización]** o **[!UICONTROL Estado]**.

![Filtros de trabajo de conjunto de clasificaciones](../assets/classification-set-job-filters.png)

Hay opciones de filtro adicionales disponibles encima de las columnas del Administrador de trabajos de conjuntos de clasificaciones:

* **[!UICONTROL Buscar por título]**: buscar trabajos por nombre de archivo.
* **[!UICONTROL Cargar más]**: el Administrador de trabajos de conjuntos de clasificaciones muestra inicialmente hasta 1000 trabajos. Haga clic en este botón para cargar 1000 trabajos más.
* **Mostrar/ocultar columnas**: alternar visibilidad para cualquier columna aparte de [!UICONTROL Nombre de archivo] y [!UICONTROL Hora de finalización].

## Columnas del Administrador de trabajos del conjunto de clasificaciones

Las siguientes columnas están disponibles en el Administrador de trabajos de conjuntos de clasificaciones:

* **[!UICONTROL Nombre de archivo]**: Nombre del archivo de carga o descarga.
* **[!UICONTROL Conjunto de clasificaciones]**: Nombre del conjunto de clasificaciones al que se aplica el archivo. Puede hacer clic en el nombre del conjunto de clasificaciones para llegar a la [Configuración](settings.md).
* **[!UICONTROL Tamaño]**: El tamaño del archivo.
* **[!UICONTROL Estado]**: estado del trabajo que procesa el archivo.
   * **[!UICONTROL Creado]**: se envió el trabajo.
   * **[!UICONTROL En cola]**: el archivo está listo para procesarse y está esperando a que un servidor de clasificación procese el archivo.
   * **[!UICONTROL Validado]**: el archivo es válido y está a la espera de ser procesado.
   * **[!UICONTROL Error de validación]**: el formato del archivo es incorrecto o no es válido. El archivo no se procesa.
   * **[!UICONTROL Procesamiento]**: Adobe está procesando activamente el archivo.
   * **[!UICONTROL Error de procesamiento]**: error en el procesamiento del archivo.
   * **[!UICONTROL Completar]**: el procesamiento ha finalizado. Los datos de clasificación se pueden ver en los informes.
   * **[!UICONTROL Error]**: error genérico no relacionado con la validación o el procesamiento.
* **[!UICONTROL Tipo]**: tipo de trabajo.
* **[!UICONTROL Descarga de archivos]**: solo se aplica a los trabajos de descarga, como descargar datos de clasificación o descargar plantillas. Cuando una descarga está lista, esta columna proporciona un vínculo de descarga.
* **[!UICONTROL Hora de finalización]**: la fecha y hora en que se completó el trabajo (o falló).
