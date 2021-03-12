---
title: Vinculación basada en el campo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante la vinculación basada en el campo.
translation-type: tm+mt
source-git-commit: beed7ffcc39b9b2628b1487b5e2eac42fa3a94d0
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 35%

---


# Vinculación basada en el campo

Cross-Device Analytics proporciona dos métodos distintos para unir datos. Este método depende de una variable de Analytics, como una [propiedad](/help/implement/vars/page-vars/prop.md) o un [eVar](/help/implement/vars/page-vars/evar.md), para contener un identificador de persona. Utiliza esa variable como base para vincular dispositivos.

## Requisitos previos específicos de la vinculación basada en el campo

Si tiene intención de implementar el análisis entre dispositivos mediante la vinculación basada en el campo, es necesario lo siguiente. Trabaje con equipos de su organización y con el administrador de cuentas de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Todos los requisitos previos enumerados en la [página de información general](overview.md).
* La implementación debe establecer una propiedad o un eVar que identifique de forma exclusiva a un individuo siempre que sea posible, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Comunique la variable de identificación que desee al administrador de cuentas cuando se aprovisione para la vinculación basada en el campo.

## Limitaciones específicas de la vinculación basada en el campo

* La vinculación basada en el campo funciona mejor en los grupos de informes que tienen una alta tasa de identificación/autenticación de usuarios.
* Aunque las props y las eVars tienen reglas para la administración de caracteres en mayúsculas y minúsculas con fines de creación de informes, la vinculación basada en el campo no transforma la propiedad o el eVar que se usa para la vinculación de ninguna manera. La vinculación basada en el campo utiliza el valor del campo especificado, ya que existe después de las reglas de VISTA y después de las reglas de procesamiento. El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, si a veces la palabra &quot;Bob&quot; aparece en el prop/eVar y a veces aparece la palabra &quot;BOB&quot;, el proceso de vinculación los tratará como dos personas separadas.
* Dado que la vinculación basada en el campo distingue entre mayúsculas y minúsculas, Adobe recomienda revisar cualquier regla de VISTA o regla de procesamiento que se aplique a la propiedad o al eVar que se esté utilizando para la vinculación basada en el campo. Deben revisarse para garantizar que ninguna de estas reglas introduzca nuevos formularios del mismo ID. Por ejemplo, debe asegurarse de que ninguna VISTA o regla de procesamiento introduce minúsculas en la prop o el eVar solo en una parte de las visitas.
* La vinculación basada en el campo no admite el uso de más de una prop o eVar con fines de vinculación. Por ejemplo, si eVar12 contiene el ID de inicio de sesión y eVar20 contiene el ID de correo electrónico, debe elegir uno de ellos.
* La vinculación basada en el campo no combina ni concatena campos (por ejemplo, eVar10 + prop5).
* La prop o el eVar deben contener un solo tipo de ID. Por ejemplo, la prop o el eVar no deben contener una combinación de ID de inicio de sesión e ID de correo electrónico.
* Si se producen varias visitas con la misma marca de tiempo para el mismo visitante, pero con valores diferentes en la propiedad de vinculación o el eVar, CDA elegirá en función del orden alfabético. Por lo tanto, si el visitante A tiene dos visitas con la misma marca de tiempo y una de las visitas especifica Bob y la otra especifica Ann, CDA elegirá Ann.


## Pasos siguientes

Una vez que su organización cumpla todos los requisitos y comprenda las limitaciones, puede iniciar [Configuración de análisis entre dispositivos](setup.md).
