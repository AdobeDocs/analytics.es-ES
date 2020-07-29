---
description: El archivo de importación y exportación incluye seis columnas para cada clasificación numérica 2.
subtopic: Classifications
title: Importar clasificaciones numéricas 2
topic: Admin tools
uuid: 82a3034c-e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 100%

---


# Importar clasificaciones numéricas 2

>[!IMPORTANT]
>
>Se ha eliminado de la base de código la posibilidad de importar clasificaciones numéricas 2 y fechas activadas. Este cambio entra en vigor con el lanzamiento de mantenimiento de julio de 2019. Si tiene columnas numéricas o con fecha habilitada en el archivo de importación, esas celdas serán omitidas sin aviso y cualquier otra información de ese archivo se importará como de costumbre. Las clasificaciones existentes se pueden exportar a través del flujo de trabajo de clasificación estándar y seguirán estando disponibles en los informes.

El archivo de importación y exportación incluye seis columnas para cada clasificación numérica 2.

Las siguientes definiciones asumen que el nombre de su clasificación numérica 2 es MyCost.

**~MyCost:** un nombre descriptivo para la fila.

**~MyCost^~id~:** El ID para editar una fila existente. Cuando añada una fila nueva, esto debería estar en blanco. Al llevar a cabo exportaciones desde el Administrador de clasificación, se asigna automáticamente un ID.

**~MyCost^~value~:** El valor de la fila. Si la columna de la tasa es fija, entonces se trata de un valor determinado que se distribuye a lo largo de todo el periodo. Si la columna de tasa es un evento, entonces es el multiplicador de dicho evento. Esta entrada no debe contener comas.

**~MyCost^~period~:** El periodo de tiempo al que corresponde esta fila. Debe incluir las fechas de inicio y finalización, separadas por un guión. El guión debe escribirse entre espacios. La definición debe tener el formato siguiente:

AAAA/MM/DD - AAAA/MM/DD

**~MyCost^~rate~:** El evento a multiplicar por la columna [!UICONTROL Valor]. Los valores válidos son:

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
* evento 1
* evento 2
* etc.

**~MyCost^~hinge~:** El evento que se debe utilizar para distribuir el valor durante un desglose. Este valor suele ser el mismo que [!UICONTROL ~MyCost^~rate~], a menos que esté utilizando [!UICONTROL fijo]. Los valores válidos para esta columna son idénticos a los de [!UICONTROL ~MyCost^~rate~], con el añadido de [!UICONTROL ninguno].
