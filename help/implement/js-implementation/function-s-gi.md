---
description: La función s_gi() se usa para crear o buscar una instancia de AppMeasurement por ID de grupo de informes. AppMeasurement realiza un seguimiento interno de todas las instancias que se crean y s_gi() devuelve la instancia de un grupo de informes, si existe. Si no existe, se crea y devuelve una nueva.
keywords: Implementación de Analytics
seo-description: La función s_gi() se usa para crear o buscar una instancia de AppMeasurement por ID de grupo de informes. AppMeasurement realiza un seguimiento interno de todas las instancias que se crean y s_gi() devuelve la instancia de un grupo de informes, si existe. Si no existe, se crea y devuelve una nueva.
seo-title: La función s_gi()
solution: Analytics
title: Función s_gi()
topic: Desarrollador e implementación
uuid: a 77 de 90 e-c 60 e -4946-90 cf-deaf 8 aa 3 d 755
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Función s_gi()

La función s_gi() se usa para crear o buscar una instancia de AppMeasurement por ID de grupo de informes. AppMeasurement realiza un seguimiento interno de todas las instancias que se crean y s_gi() devuelve la instancia de un grupo de informes, si existe. Si no existe, se crea y devuelve una nueva.

We recommend calling `s_gi()` before setting variables and making tracking calls throughout your page code. Así se garantiza que se usará el objeto correcto para realizar la llamada de seguimiento si la variable s se sobrescribe de forma involuntaria.

## Uso de varios grupos de informes {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

El objeto devuelto varía en función de la o las ID de grupo de informes que se pasan. Por ejemplo, si realiza la llamada inicial siguiente a `s_gi()`:

```
var s=s_gi('rsid1,rsid2')
```

La tabla siguiente resume los elementos que se devuelven en las llamadas subsiguientes:

| ** Llamada subsiguiente a s_ gi** | ** Descripción del objeto devuelto** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | El mismo objeto al que se ha hecho referencia anteriormente. |
| `s=s_gi('rsid1')` | Una copia del objeto creado anteriormente, pero no el objeto original. |
| `s=s_gi('rsid1,rsid3')` | Una copia del objeto creado anteriormente, pero no el objeto original. |
| `s=s_gi('rsid3')` | Un objeto nuevo vacío sin variables de configuración establecidas (por ejemplo, linkTrackVars y linkDownloadFileTypes están vacíos). |

