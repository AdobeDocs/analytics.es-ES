---
title: Configuración del conjunto de clasificaciones
description: Cree o edite un conjunto de clasificaciones.
source-git-commit: c9465ea0524225494aa5067d00ca5e7aba4bca92
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---


# Configuración del conjunto de clasificaciones

Configure un conjunto de clasificaciones, cargue datos o descargue datos.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Conjuntos]** > Haga clic en el nombre del conjunto de clasificaciones que desee

Al editar un conjunto de clasificaciones, hay dos fichas disponibles; **[!UICONTROL Esquema]** y **[!UICONTROL Configuración]**.

## Configuración 

Los campos siguientes están disponibles en la [!UICONTROL Configuración] y se puede editar:

* **[!UICONTROL Nombre]**: El nombre del conjunto de clasificaciones.
* **[!UICONTROL Descripción]**: Descripción del conjunto de clasificaciones.
* **[!UICONTROL Nombre del propietario]**: El nombre del propietario.
* **[!UICONTROL Correo electrónico del propietario]**: La dirección de correo electrónico del propietario.
* **[!UICONTROL Notificar problemas]**: Lista de direcciones de correo electrónico delimitada por comas a las que se notifican los problemas con este conjunto de clasificaciones.
* **[!UICONTROL Etiquetas]**: Agregue una o más etiquetas a los conjuntos de clasificaciones seleccionados, lo que le permite organizar o agrupar conjuntos de clasificaciones para que sean más fáciles de localizar en el futuro.

Los campos adicionales están disponibles con fines informativos y no se pueden editar:

* **[!UICONTROL Tipo]**: El tipo de clasificación entre [!UICONTROL Principal] y [!UICONTROL Búsqueda]. Las clasificaciones principales generalmente se utilizan.
* **[!UICONTROL Suscripciones]**: Grupo de informes y variable a los que se aplica el conjunto de clasificaciones. Actualmente solo se admite un grupo de informes para un conjunto de clasificaciones determinado; se ha planificado la compatibilidad con varios grupos de informes.

## Esquema

Ver las dimensiones de clasificación configuradas actualmente para esta suscripción. Los botones disponibles son los siguientes:

* **[!UICONTROL Cargar]**: Cargue manualmente los datos de clasificación de una o varias dimensiones de clasificación. Los archivos JSON, CSV, TSV y TAB son compatibles. Al cargar un archivo válido, se muestra una vista previa de tabla de los datos que se van a clasificar.
   * **[!UICONTROL Codificación de archivos]**: Seleccione la codificación de archivo correcta mediante este menú desplegable. Las opciones válidas incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1].
   * **[!UICONTROL Delimitador de lista]**: Seleccione el delimitador de lista correcto. Si utiliza un archivo de plantilla o archivo descargado, asegúrese de que [!UICONTROL Delimitador de lista] aquí coincide la variable [!UICONTROL Delimitador de lista] cuando se descargó el archivo.
   * **[!UICONTROL Aplicar]**: Guarde los datos de clasificación cargados en el conjunto de clasificaciones.
