---
title: Cómo funcionan las reproducciones
description: Comprensión del concepto "reproducción" en Cross-Device Analytics
exl-id: 0b7252ff-3986-4fcf-810a-438d9a51e01f
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/UuIRVpQJxJDKTYBg7hlNMlVG4PgGMAoD0NLdJfeQydA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 499
ht-degree: 89%

---

# Cómo funcionan las reproducciones

{{available-existing-customers}}

Cross-Device Analytics realiza dos pasadas de datos en un grupo de informes virtual:

* **Vinculación en tiempo real**: CDA intenta vincular cada visita conforme se va produciendo. Los nuevos dispositivos netos del grupo de informes que nunca han iniciado sesión no suelen vincularse en este nivel. Los dispositivos ya reconocidos se vinculan inmediatamente.
* **Reproducir**: aproximadamente una vez a la semana, CDA &quot;reproduce&quot; datos basados en identificadores únicos que ha aprendido. En esta fase es en la que se vinculan nuevos dispositivos al grupo de informes.

## Tabla de ejemplo

Las siguientes tablas ilustran cómo ([Vinculación basada en el campo](field-based-stitching.md) calcula el número de personas únicas:

### Vinculación en directo

Tan pronto como se recopila una visita, CDA intenta vincularla a dispositivos conocidos. Preste atención al siguiente ejemplo, en el que Bob utiliza dos dispositivos.

*Datos tal como aparecen el día en que se recopilan:*

| Marca de tiempo | ECID | eVar1 o CustomerID | Explicación de la visita | Métrica de personas (acumulativa) mediante vinculación basada en el campo |
| --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob con su equipo de escritorio, sin autenticar | `1` (246) |
| `2` | `246` | `Bob` | Bob inicia sesión en su equipo de escritorio | `2` (246 y Bob) |
| `3` | `3579` | - | Bob con su dispositivo móvil, sin autenticar | `3` (246, Bob y 3579) |
| `4` | `3579` | `Bob` | Bob inicia sesión en su dispositivo móvil | `3` (246, Bob y 3579) |
| `5` | `246` | - | Bob vuelve a visitar el sitio con su equipo de escritorio, sin autenticarse | `3` (246, Bob y 3579) |
| `6` | `246` | `Bob` | Bob inicia sesión de nuevo con su equipo de escritorio | `3` (246, Bob y 3579) |
| `7` | `3579` | - | Bob vuelve a acceder al sitio con su dispositivo móvil | `3` (246, Bob y 3579) |
| `8` | `3579` | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `3` (246, Bob y 3579) |

Las visitas no autenticadas y autenticadas en los nuevos dispositivos se cuentan como personas independientes (temporalmente).
Las visitas no autenticadas en dispositivos reconocidos se vinculan en directo a partir de ese momento. La atribución funciona tan pronto como la variable personalizada de identificación se vincula a un dispositivo. En el ejemplo anterior, todas las visitas, excepto la 1 y la 3, están vinculadas en tiempo real (todas utilizan el identificador `Bob`). La atribución funciona en las visitas 1 y 3 tras la reproducción de la vinculación.

>[!NOTE]
>
>Las visitas con marca de tiempo de más de 12 horas no se identifican en el flujo en directo. Sin embargo, estas visitas se incluyen en la identificación de Reproducción, siempre que entren en la ventana de retrospectiva de reproducción.

### Reproducción de la vinculación

La reproducción tiene lugar diaria o semanalmente, en función de cómo haya solicitado que se configure CDA. Durante la reproducción, CDA intenta reiterar los datos históricos en un periodo de tiempo retrospectivo definido:

* La reproducción diaria utiliza un periodo restrospectivo de 1 día
* La reproducción semanal utiliza un periodo retrospectivo de 7 días.

Si un dispositivo envía inicialmente datos sin autenticarse y, luego, inicia sesión, CDA vincula esas visitas sin autenticar con la persona correcta. La siguiente tabla representa los mismos datos que arriba, pero muestra números diferentes basados en la reproducción de los datos.

*Los mismos datos después de la reproducción:*

| Marca de tiempo | ECID | eVar1 o CustomerID | Explicación de la visita | Métrica de personas (acumulativa) mediante vinculación basada en el campo |
| --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob con su equipo de escritorio, sin autenticar | `1` (Bob) |
| `2` | `246` | `Bob` | Bob inicia sesión en su equipo de escritorio | `1` (Bob) |
| `3` | `3579` | - | Bob con su dispositivo móvil, sin autenticar | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob inicia sesión en su dispositivo móvil | `1` (Bob) |
| `5` | `246` | - | Bob vuelve a visitar el sitio con su equipo de escritorio, sin autenticarse | `1` (Bob) |
| `6` | `246` | `Bob` | Bob inicia sesión de nuevo con su equipo de escritorio | `1` (Bob) |
| `7` | `3579` | - | Bob vuelve a acceder al sitio con su dispositivo móvil | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `1` (Bob) |
