---
description: Las clasificaciones numéricas 2 ofrecen métricas personalizadas y flexibles que puede importar en Adobe Experience Cloud a través del importador.
seo-description: Las clasificaciones numéricas 2 ofrecen métricas personalizadas y flexibles que puede importar en Adobe Experience Cloud a través del importador.
seo-title: Resumen de clasificaciones numéricas 2
solution: Analytics
subtopic: Clasificaciones
title: Resumen de clasificaciones numéricas 2
topic: Herramientas de administración
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Resumen de clasificaciones numéricas 2

Las clasificaciones numéricas 2 ofrecen métricas personalizadas y flexibles que puede importar en Adobe Experience Cloud a través del importador.

>[!IMPORTANT]
>
>Se ha eliminado de la base de código la posibilidad de importar clasificaciones numéricas 2 y fechas activadas. Este cambio entra en vigor con el lanzamiento de mantenimiento de julio de 2019. Si tiene columnas numéricas o con fecha habilitada en el archivo de importación, esas celdas serán omitidas sin aviso y cualquier otra información de ese archivo se importará como de costumbre. Las clasificaciones existentes se pueden exportar a través del flujo de trabajo de clasificación estándar y seguirán estando disponibles en los informes.

>[!NOTE]
>
>En la versión de mantenimiento de Analytics del 10 de mayo de 2018, Adobe comenzó a limitar la funcionalidad de las clasificaciones numéricas y con fecha habilitada. Estos tipos de clasificaciones se eliminaron de las interfaces del Administrador y del Importador de clasificaciones. No es posible añadir nuevas clasificaciones numéricas y habilitadas por fecha. Las clasificaciones existentes se podrán seguir administrando (cargado y eliminado) a través del flujo de trabajo de clasificación estándar y permanecerán disponibles en los informes.

Las clasificaciones numéricas 2 se suelen utilizar con variables numéricas que cambian con el tiempo y con diferentes artículos, como el coste de los bienes que se venden. En la administración, puede crear clasificaciones en la página [!UICONTROL Clasificación de conversión] y, a continuación, usar el importador para exportar un archivo, realizar cambios y, después, volver a importar el archivo en Adobe. Una vez importados los datos, al crear métricas calculadas puede utilizar las clasificaciones numéricas.

>[!IMPORTANT]
>
>Analysis Workspace y Análisis específicos no admiten clasificaciones numéricas 2.

En la siguiente tabla se muestran las diferencias entre los tipos de clasificación:

| FUNCIÓN | TEXTO | NUMÉRICA 1.0 | NUMÉRICA 2.0 |
|---|---|---|---|
| Aparece como un informe | Sí | No | No |
| Puede utilizarse como métrica | No | Sí | Sí |
| Puede crearse en el informe de base | Sí | No | Sí |
| Calculado en función de los eventos | No | Sí | Sí |
| Múltiples filas por clave | No | No | Sí |
| Puede tener valores diferentes para periodos de tiempo diferentes | No | No | Sí |
| Puede utilizarse en métricas calculadas | No | Sí | Sí |

