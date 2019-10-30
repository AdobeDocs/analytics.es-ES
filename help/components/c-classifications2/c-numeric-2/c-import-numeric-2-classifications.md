---
description: El archivo de importación y exportación incluye seis columnas para cada clasificación numérica 2.
seo-description: El archivo de importación y exportación incluye seis columnas para cada clasificación numérica 2.
seo-title: Importar clasificaciones numéricas 2
solution: Analytics
subtopic: Clasificaciones
title: Importar clasificaciones numéricas 2
topic: Herramientas de administración
uuid: 82a3034c-e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Importar clasificaciones numéricas 2

>[!IMPORTANT]
>
>Se ha eliminado de la base de código la posibilidad de importar clasificaciones numéricas 2 y fechas activadas. Este cambio entra en vigor con el lanzamiento de mantenimiento de julio de 2019. Si tiene columnas numéricas o con fecha habilitada en el archivo de importación, esas celdas serán omitidas sin aviso y cualquier otra información de ese archivo se importará como de costumbre. Las clasificaciones existentes se pueden exportar a través del flujo de trabajo de clasificación estándar y seguirán estando disponibles en los informes.

El archivo de importación y exportación incluye seis columnas para cada clasificación numérica 2.

Las siguientes definiciones asumen que el nombre de su clasificación numérica 2 es MyCost.

**~MyCost:** un nombre descriptivo para la fila.

**~~MyCost^~id**: ID para editar una fila existente. Cuando añada una fila nueva, esto debería estar en blanco. Al llevar a cabo exportaciones desde el Administrador de clasificación, se asigna automáticamente un ID.

**~~MyCost^~value**: Valor de la fila. Si la columna de la tasa es fija, entonces se trata de un valor determinado que se distribuye a lo largo de todo el periodo. Si la columna de tasa es un evento, entonces es el multiplicador de dicho evento. Esta entrada no debe contener comas.

**~~MyCost^~period**: Período de tiempo al que corresponde esta fila. Debe incluir las fechas de inicio y finalización, separadas por un guión. El guión debe escribirse entre espacios. La definición debe tener el formato siguiente:

AAAA/MM/DD - AAAA/MM/DD

**~~MyCost^~rate**: Evento que se multiplicará por la columna [!UICONTROL Valor] . Los valores válidos son:

* fijo: para indicar que se trata de un valor único que debe propagarse a lo largo del periodo.
* revenue
* order
* unit
* scopen
* scviews
* instance
* click
* checkout
* scadd
* scremove
* event 1
* event 2
* etc.

**~~MyCost^~hinge**: Evento que se utiliza para distribuir el valor durante un desglose. This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none].
