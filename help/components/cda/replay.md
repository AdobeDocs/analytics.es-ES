---
title: Cómo funcionan las reproducciones
description: Comprender el concepto de "repetición" en Análisis entre dispositivos
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---


# Cómo funcionan las reproducciones

Análisis entre dispositivos realiza dos pasadas de datos en un grupo de informes virtuales:

* **Cosificación** en vivo: CDA intenta unir cada visita a medida que entra. Los nuevos dispositivos netos del grupo de informes que nunca han iniciado sesión no suelen vincularse a este nivel. Los dispositivos ya reconocidos se vinculan inmediatamente.
* **Reproducir**: Aproximadamente una vez a la semana, CDA &quot;reproduce&quot; datos basados en identificadores únicos que ha aprendido. En esta etapa se vinculan nuevos dispositivos al grupo de informes.

## Tabla de ejemplo

Las siguientes tablas ilustran cómo los métodos CDA ([Colisión basada en campo](field-based-stitching.md) y [Gráfico de dispositivos](device-graph.md)) calculan el número de personas únicas:

### Coherencia en vivo

Tan pronto como se recopila una visita, CDA intenta vincularla a dispositivos conocidos. Considere el siguiente ejemplo, donde Bob utiliza dos dispositivos.

*Datos tal como aparecen el día en que se recopilan:*

| Marca de tiempo | ECID | eVar1 o CustomerID | Explicación de la visita | Métrica Personas (acumulativa) mediante Device Graph | Métrica Personas (acumulativa) mediante la vinculación basada en campos |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob en su equipo de escritorio, sin autenticar | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob inicia sesión en su escritorio | `1` (246) | `2` (246 y Bob) |
| `3` | `3579` | - | Bob en su dispositivo móvil, sin autenticar | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `4` | `3579` | `Bob` | Bob inicia sesión en móvil | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `5` | `246` | - | Bob vuelve a acceder al sitio en el escritorio, sin autenticar | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `6` | `246` | `Bob` | Bob inicia sesión de nuevo en el escritorio | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `7` | `3579` | - | Bob vuelve a acceder al sitio en dispositivos móviles | `2` (246 y 3579) | `3` (246, Bob y 3579) |
| `8` | `3579` | `Bob` | Bob inicia sesión de nuevo a través del dispositivo móvil | `2` (246 y 3579) | `3` (246, Bob y 3579) |

Tanto las visitas autenticadas como las no autenticadas en los nuevos dispositivos se cuentan como personas independientes (temporalmente).

* **Si se utiliza el gráfico del dispositivo, las visitas** no autenticadas en dispositivos reconocidos se vinculan en directo una vez que el gráfico del dispositivo publica un clúster. La publicación de clústeres tarda entre tres horas y dos semanas.

   También se agrega una tercera persona acumulativa cuando se publica un clúster. Esta tercera persona representa el propio clúster, además de los dispositivos individuales. Esta tercera &quot;persona&quot; permanece hasta que se reproduzcan los datos.

   La atribución no funciona en todos los dispositivos hasta que se publica un clúster, e incluso entonces solo se vinculan en directo a partir de ese momento. En el ejemplo anterior, ninguna de las visitas se ha vinculado aún entre dispositivos. La atribución entre dispositivos en las visitas individuales existentes no funciona hasta después de la reedición de la vinculación.
* **Si se utiliza la vinculación basada en campos, las visitas** no autenticadas en dispositivos reconocidos se vinculan en directo a partir de ese momento.

   La atribución funciona tan pronto como la variable personalizada de identificación se vincula a un dispositivo. En el ejemplo anterior, todas las visitas individuales excepto las visitas individuales 1 y 3 están vinculadas en directo (todas utilizan el identificador `Bob`). La atribución funciona en las visitas individuales 1 y 3 después de la reproducción.

### Reproducir la vinculación

Aproximadamente una vez por semana, CDA vuelve a calcular los datos históricos en función de los dispositivos que ahora reconoce. Si un dispositivo envía inicialmente datos sin autenticar y luego inicia sesión, CDA vincula esas visitas sin autenticar con la persona correcta. La siguiente tabla representa los mismos datos que arriba, pero muestra números diferentes basados en la reproducción de los datos.

*Los mismos datos después de la reproducción:*

| Marca de tiempo | ECID | eVar1 o CustomerID | Explicación de la visita | Métrica Personas (acumulativa) mediante Device Graph | Métrica Personas (acumulativa) mediante la vinculación basada en campos |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob en su equipo de escritorio, sin autenticar | `1` (Cluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob inicia sesión en su escritorio | `1` (Cluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob en su dispositivo móvil, sin autenticar | `1` (Cluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob inicia sesión en móvil | `1` (Cluster1) | `1` (Bob) |
| `5` | `246` | - | Bob vuelve a acceder al sitio en el escritorio, sin autenticar | `1` (Cluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob inicia sesión de nuevo en el escritorio | `1` (Cluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob vuelve a acceder al sitio en dispositivos móviles | `1` (Cluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob inicia sesión de nuevo a través del dispositivo móvil | `1` (Cluster1) | `1` (Bob) |

## Volver a poner

* **Si se utiliza Device Graph,** los datos se vinculan cuando se publica un clúster (normalmente de 3 a 2 semanas).
* **Si se utiliza la vinculación basada en campo,** los datos de menos de una semana de antigüedad vinculan inmediatamente a dispositivos conocidos, pero no se acoplan inmediatamente a dispositivos nuevos o no reconocidos.
* Los datos se reproducen una vez por semana y cambian los datos históricos en el grupo de informes virtuales en función de los dispositivos que ha aprendido a identificar.
