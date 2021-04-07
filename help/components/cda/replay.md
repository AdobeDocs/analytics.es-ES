---
title: Cómo funcionan las reproducciones
description: Comprensión del concepto "reproducción" en Cross-Device Analytics
translation-type: ht
source-git-commit: f3f5f82a236d376eda07d4d39e7effa60e929499
workflow-type: ht
source-wordcount: '589'
ht-degree: 100%

---


# Cómo funcionan las reproducciones

Cross-Device Analytics realiza dos pasadas de datos en un grupo de informes virtual:

* **Vinculación en tiempo real**: CDA intenta vincular cada visita conforme se va produciendo. Los nuevos dispositivos netos del grupo de informes que nunca han iniciado sesión no suelen vincularse en este nivel. Los dispositivos ya reconocidos se vinculan inmediatamente.
* **Reproducir**: aproximadamente una vez a la semana, CDA &quot;reproduce&quot; datos basados en identificadores únicos que ha aprendido. En esta fase es en la que se vinculan nuevos dispositivos al grupo de informes.

## Tabla de ejemplo

Las siguientes tablas ilustran cómo los métodos de CDA ([vinculación basada en campos](field-based-stitching.md) y [gráfico de dispositivos](device-graph.md)) calculan la cantidad de personas únicas:

### Vinculación en directo

Tan pronto como se recopila una visita, CDA intenta vincularla a dispositivos conocidos. Preste atención al siguiente ejemplo, en el que Bob utiliza dos dispositivos.

*Datos tal como aparecen el día en que se recopilan:*

| Marca de tiempo | ECID | eVar1 o CustomerID | Explicación de la visita | Métrica de personas (acumulativa) mediante el gráfico de dispositivo | Métrica de personas (acumulativa) mediante vinculación basada en campos |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob con su equipo de escritorio, sin autenticar | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob inicia sesión en su equipo de escritorio | `1` (246) | `2` (246 y Bob) |
| `3` | `3579` | - | Bob con su dispositivo móvil, sin autenticar | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `4` | `3579` | `Bob` | Bob inicia sesión en su dispositivo móvil | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `5` | `246` | - | Bob vuelve a visitar el sitio con su equipo de escritorio, sin autenticarse | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `6` | `246` | `Bob` | Bob inicia sesión de nuevo con su equipo de escritorio | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `7` | `3579` | - | Bob vuelve a acceder al sitio con su dispositivo móvil | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `8` | `3579` | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `2` (246 y 3579) | `3` (246, Bob y 3579) |

Tanto las visitas no autenticadas como las autenticadas en los nuevos dispositivos se cuentan como personas independientes (temporalmente).

* **Si se utiliza el gráfico de dispositivo**, las visitas no autenticadas en dispositivos reconocidos se vinculan en directo una vez que el gráfico del dispositivo publica un grupo. La publicación de grupos tarda entre tres horas y dos semanas.

   También se agrega una tercera persona acumulativa cuando se publica un grupo. Esta tercera persona representa el propio grupo, además de los dispositivos individuales. Esta tercera &quot;persona&quot; permanece hasta que se reproduzcan los datos.

   La atribución no funciona en todos los dispositivos hasta que se publica un grupo e incluso entonces solo se vinculan en directo a partir de ese momento. En el ejemplo anterior, ninguna de las visitas se ha vinculado aún entre dispositivos. La atribución entre dispositivos en relación con las visitas individuales existentes no funciona hasta después de la reproducción de la vinculación.
* **Si se utiliza la vinculación basada en campos,** las visitas no autenticadas en dispositivos reconocidos se vinculan en directo a partir de ese momento.

   La atribución funciona tan pronto como la variable personalizada de identificación se vincula a un dispositivo. En el ejemplo anterior, todas las visitas, excepto la 1 y la 3, están vinculadas en tiempo real (todas utilizan el identificador `Bob`). La atribución funciona en las visitas 1 y 3 tras la reproducción de la vinculación.

### Reproducción de la vinculación

La reproducción tiene lugar diaria o semanalmente, en función de cómo haya solicitado que se configure CDA. Durante la reproducción, CDA intenta reiterar los datos históricos en un periodo de tiempo retrospectivo definido:

* La reproducción diaria utiliza un periodo restrospectivo de 1 día
* La reproducción semanal utiliza un periodo retrospectivo de 7 días.

Si un dispositivo envía inicialmente datos sin autenticarse y, luego, inicia sesión, CDA vincula esas visitas sin autenticar con la persona correcta. La siguiente tabla representa los mismos datos que arriba, pero muestra números diferentes basados en la reproducción de los datos.

*Los mismos datos después de la reproducción:*

| Marca de tiempo | ECID | eVar1 o CustomerID | Explicación de la visita | Métrica de personas (acumulativa) mediante el gráfico de dispositivo | Métrica de personas (acumulativa) mediante vinculación basada en campos |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob con su equipo de escritorio, sin autenticar | `1` (Cluster1) | `1` |
| `2` | `246` | `Bob` | Bob inicia sesión en su equipo de escritorio | `1` (Cluster1) | `1` |
| `3` | `3579` | - | Bob con su dispositivo móvil, sin autenticar | `1` (Cluster1) | `1` |
| `4` | `3579` | `Bob` | Bob inicia sesión en su dispositivo móvil | `1` (Cluster1) | `1` |
| `5` | `246` | - | Bob vuelve a visitar el sitio con su equipo de escritorio, sin autenticarse | `1` (Cluster1) | `1` |
| `6` | `246` | `Bob` | Bob inicia sesión de nuevo con su equipo de escritorio | `1` (Cluster1) | `1` |
| `7` | `3579` | - | Bob vuelve a acceder al sitio con su dispositivo móvil | `1` (Cluster1) | `1` |
| `8` | `3579` | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `1` (Cluster1) | `1` |
