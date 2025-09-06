---
description: Formatos de archivo admitidos por los conjuntos de clasificaciones
title: Formatos de archivo del conjunto de clasificaciones
feature: Classifications
source-git-commit: 2d9eb9179ace40a8d333883cea78dd67329078ab
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 1%

---

# Formatos de archivo del conjunto de clasificaciones

Los conjuntos de clasificaciones admiten varios formatos de archivo para la carga masiva de datos de clasificación. Cada formato tiene requisitos específicos para que las cargas de datos se realicen correctamente.

Una vez que el archivo tenga el formato correcto según estas especificaciones, puede cargarlo a través de la interfaz o la API de conjuntos de clasificaciones. Para obtener instrucciones detalladas de carga:

* **Carga del explorador**: vea [Esquema](manage/schema.md)
* **Carga de API**: Consulte [API de clasificaciones de Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

Los conjuntos de clasificaciones admiten los siguientes formatos de archivo:

* **JSON**: archivos de notación de objetos de JavaScript con datos estructurados
* **CSV**: archivos de valores separados por comas
* **TSV/TAB**: archivos de valores separados por tabulaciones

## Requisitos generales de archivo

Todos los formatos de archivo deben cumplir los siguientes requisitos:

* **Codificación de archivos**: utilice UTF-8 sin marcas de orden de bytes. También se admite la codificación Latin1.
* **Límites de caracteres**: Los valores de clasificación individuales tienen un límite máximo de 255 bytes.
* **Requisitos de clave**: los valores de clave no pueden estar vacíos ni contener solo espacios en blanco. Si hay claves duplicadas, se utiliza la última ocurrencia.

+++**Detalles de formato JSON**

El formato de archivo JSON sigue las convenciones de las líneas JSON (JSONL). El archivo debe contener un objeto JSON por línea, donde cada objeto representa un único registro de clasificación.

>[!NOTE]
>
>A pesar de las siguientes convenciones para líneas JSON, utilice la extensión de archivo `.json` para todas las cargas. El uso de la extensión `.jsonl` puede provocar errores.

### Estructura JSON

Cada objeto JSON debe contener:

* `key` (obligatorio): El identificador único del registro de clasificación
* `data` (requerido para actualizaciones): un objeto que contiene nombres de columnas de clasificación y sus valores
* `action` (opcional): la acción que se va a realizar. Los valores admitidos son: 
   * `update` (predeterminado)
   * `delete-field`
   * `delete-key`
* `enc` (opcional): especificación de codificación de datos. Los valores admitidos son: 
   * `utf8` o `UTF8` (predeterminado)
   * `latin1` o `LATIN1`

Todos los nombres de campo JSON (`key`, `data`, `action`, `enc`) distinguen entre mayúsculas y minúsculas y deben escribirse en minúsculas.

### Ejemplos de JSON

**Registro de actualización básica:**

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

**Actualización con codificación especificada:**

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

**Eliminar campos específicos:**

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

**Eliminar toda la clave:**

```json
{"key": "product999", "action": "delete-key"}
```

### Reglas de validación de JSON

* El campo `key` es obligatorio y no puede ser nulo ni estar vacío.
* Para las acciones `update`, el campo `data` es obligatorio y no puede estar vacío.
* Para las acciones `delete-field`, el campo `data` debe contener los campos que se van a eliminar.
* Para las acciones `delete-key`, el campo `data` no debe estar presente.
* Los valores de codificación admitidos no distinguen entre mayúsculas y minúsculas e incluyen nombres de conjuntos de caracteres estándar.

+++

+++**Detalles de formato CSV**

Los archivos CSV (valores separados por comas) utilizan comas para separar los campos de datos de clasificación.

### Estructura CSV

* **Fila de encabezado**: la primera fila debe contener encabezados de columna y la primera columna debe ser la columna de clave. Las columnas posteriores deben coincidir con los nombres del esquema del conjunto de clasificaciones.
* **Filas de datos**: Cada fila subsiguiente contiene datos de clasificación
* **Delimitadores**: los campos están separados por comas
* **Comillas**: los campos que contienen comas, comillas o líneas nuevas deben escribirse entre comillas dobles

### Ejemplos de CSV

**Datos básicos de clasificación:**

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

**Eliminar toda la clave:**

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

**Eliminar campos específicos (mezclados con actualizaciones):**

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

### Reglas de formato CSV

* Los campos que contienen comas deben ir entre comillas dobles
* Los campos que contienen comillas dobles deben escapar de las comillas duplicándolas (`""`)
* Los campos vacíos representan valores nulos para esa clasificación
* Los espacios iniciales y finales alrededor de los campos se recortan automáticamente
* Se conservan los caracteres especiales (pestañas, líneas nuevas) dentro de los campos entre comillas

**Eliminar operaciones:**
* Use `~deletekey~` en cualquier campo para eliminar toda la clave y todos sus datos de clasificación
* Utilice `~empty~` en campos específicos para eliminar solo esos valores de clasificación (deja otros campos intactos)
* Al usar `~empty~`, puede combinar eliminaciones con actualizaciones en el mismo archivo

+++

+++**Detalles de formato TSV/TAB**

Los archivos TSV (valores separados por tabulaciones) y TAB utilizan caracteres de tabulación para separar los campos de datos de clasificación.

### Estructura de TSV/TAB

* **Fila de encabezado**: la primera fila debe contener encabezados de columna y la primera columna debe ser la columna de clave. Las columnas posteriores deben coincidir con los nombres del esquema del conjunto de clasificaciones.
* **Filas de datos**: Cada fila subsiguiente contiene datos de clasificación
* **Delimitadores**: los campos están separados por caracteres de tabulación (`\t`)
* **Citación**: Generalmente no se necesita entrecomillado, pero algunas implementaciones admiten campos entre comillas

### Ejemplos de TSV/TAB

**Datos básicos de clasificación:**

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

**Eliminar toda la clave:**

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

**Eliminar campos específicos (mezclados con actualizaciones):**

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

### Reglas de formato TSV/TAB

* Los campos están separados por caracteres de una sola pestaña
* Los campos vacíos (pestañas consecutivas) representan valores nulos
* No suele ser necesario un presupuesto especial
* Se conservan los espacios iniciales y finales
* Deben evitarse los caracteres de nueva línea dentro de los campos

**Eliminar operaciones:**
* Use `~deletekey~` en cualquier campo para eliminar toda la clave y todos sus datos de clasificación
* Utilice `~empty~` en campos específicos para eliminar solo esos valores de clasificación (deja otros campos intactos)
* Al usar `~empty~`, puede combinar eliminaciones con actualizaciones en el mismo archivo

+++

## Control de errores

Problemas y soluciones comunes de carga:

### Errores generales de formato de archivo

* **Formato de archivo no válido**: compruebe que la extensión de archivo coincide con el formato de contenido (.json, .csv, .tsv o .tab).
* **&quot;Encabezado desconocido&quot;**: los nombres de columna deben coincidir con el esquema del conjunto de clasificaciones (se aplica a todos los formatos).

### Errores específicos de CSV/TSV

* **&quot;Se requiere que la primera columna sea la clave&quot;**: Asegúrese de que el archivo CSV/TSV tenga una fila de encabezado adecuada con la columna clave primero.
* **&quot;Se requiere un mínimo de dos elementos de encabezado&quot;**: Los archivos CSV/TSV deben tener al menos una columna &quot;Clave&quot; y una columna de clasificación.
* **&quot;La primera columna de encabezado debe llamarse &#39;Key&#39;&quot;**: El encabezado de la primera columna debe ser exactamente &quot;Key&quot; (mayúscula K, distingue mayúsculas de minúsculas).
* **&quot;No se permiten encabezados en blanco&quot;**: todos los encabezados de columna CSV/TSV deben tener nombres.
* **&quot;El número de columnas no coincide con los encabezados&quot;**: cada fila de datos CSV/TSV debe tener el mismo número de campos que la fila de encabezado.
* **&quot;Documento mal formado&quot;**: compruebe el entrecomillado del CSV, la separación correcta de tabulaciones en los archivos TSV, etc.

### Errores específicos de JSON

* **&quot;La clave es un campo obligatorio&quot;**: Todos los registros JSON deben tener un campo `"key"` no vacío (en minúsculas, con distinción de mayúsculas y minúsculas).
* **&quot;Los datos son un campo obligatorio al usar action=update&quot;**: las acciones de actualización de JSON deben incluir un campo `"data"`.
* **&quot;Los datos son un campo obligatorio al usar action=delete-field&quot;**: las acciones de eliminar campos JSON deben especificar qué campos eliminar en el campo `"data"`.
* **&quot;Los datos no deben estar presentes al usar action=delete-key&quot;**: las acciones de eliminar clave JSON no pueden incluir un campo `"data"`.
* **&quot;Codificación no admitida&quot;**: use solo valores de codificación admitidos en el campo `"enc"` (utf8, UTF8, latin1, LATIN1).
* **Sintaxis JSON no válida**: Asegúrese de que el archivo JSON tiene el formato correcto según las convenciones JSONL. Compruebe también si hay formato JSON general, comillas, comas, corchetes, etc.

### Errores de límite de tamaño

* **&quot;La clave supera el tamaño máximo&quot;**: las claves individuales no pueden superar los 255 bytes.
* **&quot;El valor de columna supera el tamaño máximo&quot;**: Los valores de clasificación individual no pueden superar los 255 bytes.

## Prácticas recomendadas

* **Tamaño de archivo**: 50 MB es el tamaño máximo de archivo para las cargas de explorador y API.
* **Procesamiento por lotes**: Para conjuntos de datos grandes, considere la posibilidad de dividirlos en archivos más pequeños.
* **Validación de datos**: realice pruebas con un archivo de muestra pequeño antes de cargar conjuntos de datos grandes.
* **Copia de seguridad**: conserve copias de los archivos de datos de origen.
* **Actualizaciones incrementales**: use el formato JSON para un control preciso de las actualizaciones y eliminaciones de registros individuales.
