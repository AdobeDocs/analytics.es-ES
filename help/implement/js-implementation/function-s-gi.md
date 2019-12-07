---
description: La función s_gi() se usa para crear o buscar una instancia de AppMeasurement por ID de grupo de informes. AppMeasurement realiza un seguimiento interno de todas las instancias que se crean y s_gi() devuelve la instancia de un grupo de informes, si existe. Si no existe, se crea y devuelve una nueva.
keywords: Analytics Implementation
title: Función s_gi()
topic: Developer and implementation
uuid: a77de90e-c60e-4946-90cf-deaf8aa3d755
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Función s_gi()

La función s_gi() se usa para crear o buscar una instancia de AppMeasurement por ID de grupo de informes. AppMeasurement realiza un seguimiento interno de todas las instancias que se crean y s_gi() devuelve la instancia de un grupo de informes, si existe. Si no existe, se crea y devuelve una nueva.

Recomendamos llamar a `s_gi()` antes de establecer las variables y realizar las llamadas de seguimiento a través del código de página. Así se garantiza que se usará el objeto correcto para realizar la llamada de seguimiento si la variable s se sobrescribe de forma involuntaria.

## Uso de varios grupos de informes {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

El objeto devuelto varía en función de la o las ID de grupo de informes que se pasan. Por ejemplo, si realiza la llamada inicial siguiente a `s_gi()`:

```
var s=s_gi('rsid1,rsid2')
```

La tabla siguiente resume los elementos que se devuelven en las llamadas subsiguientes:

| **Llamada subsiguiente a s_gi** | **Descripción del objeto que se devuelve** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | El mismo objeto al que se ha hecho referencia anteriormente. |
| `s=s_gi('rsid1')` | Una copia del objeto creado anteriormente, pero no el objeto original. |
| `s=s_gi('rsid1,rsid3')` | Una copia del objeto creado anteriormente, pero no el objeto original. |
| `s=s_gi('rsid3')` | Un objeto nuevo vacío sin variables de configuración establecidas (por ejemplo, linkTrackVars y linkDownloadFileTypes están vacíos). |
