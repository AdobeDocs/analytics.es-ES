---
description: Valide que la integración captura correctamente los datos comprobando el seguimiento en directo y los informes.
seo-description: Valide que la integración captura correctamente los datos comprobando el seguimiento en directo y los informes.
seo-title: Verificación de la integración
title: Verificación de la integración
uuid: a 9 a 0746 a -4845-41 ae -919 e-e 85 d 95 c 305 be
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Verificación de la integración{#verifying-the-integration}

Valide que la integración captura correctamente los datos comprobando el seguimiento en directo y los informes.

## Seguimiento en directo {#section-9c20e8ff6b404ae09387ee07d675c9e2}

Utilice la herramienta digitalpulse Debugger para verificar que los datos de dimensión de Demandbase se envían a Adobe Analytics. Después de eliminar las cookies, vuelva a cargar una página en el sitio Web donde se haya implementado el código de integración. Suponiendo que los mapas IP actuales se asignan a una organización reconocida por Demandbase, debería ver resultados similares a los siguientes.

**Informes y análisis (anteriormente sitecatalyst) incluye las dos variables de datos de contexto Demandbase:**

![](assets/debugger1.png)

** Mbox de Target incluye los parámetros de Perfil Demandbase: **

Solo verá esto si tiene Target implementado en la página Y tiene esta integración configurada para Adobe Target. Consulte el paso 4 en el Asistente de integración de Adobe.

![](assets/debugger2.png)

## Informes {#section-1792fe75dc3249d0ad063dfd87a89162}

Revise los informes Demandbase en Adobe Analytics mediante el panel que se creó automáticamente mediante el Asistente de integración de Adobe (Paso 7).

También puede navegar a los informes de Demandbase dentro de la estructura de menú de Adobe Analytics. Consulte capturas de pantalla a continuación.

>[!NOTE]
>
>Estos datos deben aparecer entre 24 y 48 horas después de la implementación correcta.

![](assets/reporting1.png)

![](assets/reporting2.png)

## Preguntas frecuentes {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**¿Qué significa "[n/a]"?**

El Conector de datos Demandbase indica cuándo un atributo es «No disponible» configurando este valor predeterminado. Existen dos escenarios comunes en los que se establece el valor predeterminado:

* Demandbase detecta que el visitante proviene de una dirección IP que no pertenece a una empresa.
* Se utiliza un atributo Watch Watch (comenzando con «watch_ list»), pero la empresa no se encuentra en la lista Watch Watch.

**¿Por qué aparece «[n/a]» con más frecuencia para ciertos atributos? **

Demandbase clasifica todas las direcciones IP y proporciona los atributos audiencia y audience_ segment incluso cuando el visitante no proviene de una IP de empresa. Cuando la audiencia devuelve valores como «Residencial», «Inalámbrico» y «Hospitalidad», es probable que los demás atributos no estén disponibles.

A veces, la audiencia de un visitante será «SMB», pero otros atributos mostrarán «[n/a]». Esto significa que Demandbase puede clasificar al visitante como un negocio pequeño, pero el perfil de empresa completo no está disponible. Esto suele ocurrir para las empresas más pequeñas, cuando más de una pequeña empresa utiliza el mismo proveedor de servicio o bloque de direcciones IP.

## Consideraciones para desarrolladores {#section-d33fff55bc4b4db99f82dee418ef1bc2}

Si necesita ajustar el valor predeterminado en la implementación, actualice la línea:

```
_db._nonOrgMatchLabel = "[n/a]";
```

