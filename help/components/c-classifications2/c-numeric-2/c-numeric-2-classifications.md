---
description: Las clasificaciones numéricas 2 ofrecen métricas personalizadas y flexibles que puede importar en Adobe Experience Cloud a través del importador.
subtopic: Classifications
title: Resumen de clasificaciones numéricas 2
topic: Admin tools
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Resumen de clasificaciones numéricas 2

Las clasificaciones numéricas 2 ofrecen métricas personalizadas y flexibles que puede importar en Adobe Experience Cloud a través del importador.

>[!IMPORTANT]
>
>Se ha eliminado de la base de código la posibilidad de importar clasificaciones numéricas 2 y fechas activadas. Este cambio entra en vigor con el lanzamiento de mantenimiento de julio de 2019. Si tiene columnas numéricas o con fecha habilitada en el archivo de importación, esas celdas serán omitidas sin aviso y cualquier otra información de ese archivo se importará como de costumbre. Las clasificaciones existentes se pueden exportar a través del flujo de trabajo de clasificación estándar y seguirán estando disponibles en los informes.

>[!NOTE]En la versión de mantenimiento de Analytics del 10 de mayo de 2018, Adobe empezó a limitar la funcionalidad de las clasificaciones numéricas y habilitadas por fecha. Estos tipos de clasificaciones se eliminaron de las interfaces del Administrador y del Importador de clasificaciones. No se pueden agregar nuevas clasificaciones numéricas ni con fecha habilitada. Las clasificaciones existentes se podrán seguir administrando (cargado y eliminado) a través del flujo de trabajo de clasificación estándar y permanecerán disponibles en los informes.

Una manera común de utilizar las clasificaciones numéricas 2 es para variables numéricas que cambian con el tiempo para diferentes artículos, como el costo de los bienes vendidos. En la administración, puede crear clasificaciones en la [!UICONTROL Conversion Classification] página y, a continuación, utilizar el importador para exportar un archivo, realizar modificaciones y, a continuación, volver a importar el archivo en Adobe. Después de importar los datos, puede utilizar las clasificaciones numéricas al crear métricas calculadas.

>[!IMPORTANT]
>
>Analysis Workspace y Ad Hoc Analysis no admiten clasificaciones numéricas 2.

La siguiente tabla ilustra las diferencias entre los tipos de clasificación:

| FUNCIÓN | TEXTO | NUMÉRICA 1.0 | NUMÉRICA 2.0 |
|---|---|---|---|
| Se muestra como un informe | Sí | No | No |
| Se puede usar como métrica | No | Sí | Sí |
| Se puede crear en el informe base | Sí | No | Sí |
| Calculado en función de eventos | No | Sí | Sí |
| Varias filas por clave | No | No | Sí |
| Puede tener diferentes valores para diferentes períodos de tiempo | No | No | Sí |
| Se puede utilizar en métricas calculadas | No | Sí | Sí |

