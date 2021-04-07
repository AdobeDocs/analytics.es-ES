---
title: Vinculación basada en el campo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante la vinculación basada en el campo.
translation-type: ht
source-git-commit: beed7ffcc39b9b2628b1487b5e2eac42fa3a94d0
workflow-type: ht
source-wordcount: '499'
ht-degree: 100%

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

* La vinculación basada en campos funciona mejor en los grupos de informes que tienen una alta tasa de identificación/autenticación de usuarios.
* Aunque las props y eVars tienen reglas para la administración de caracteres en mayúsculas y minúsculas destinadas a la creación de informes, la vinculación basada en el campo no transforma la prop o eVar que se usa para la vinculación de ninguna manera. La vinculación basada en campos utiliza el valor del campo especificado, ya que existe después de las reglas de VISTA y después de las reglas de procesamiento. El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, si en el campo unas veces aparece la palabra &quot;Bob&quot; y otras la palabra &quot;BOB&quot;, estas se tratarán como dos personas independientes en el proceso de vinculación.
* Dado que la vinculación basada en campos distingue entre mayúsculas y minúsculas, Adobe recomienda revisar las reglas de VISTA o de procesamiento que se apliquen a la prop o eVar que se esté utilizando para la vinculación basada en campos. Deben revisarse para garantizar que ninguna de estas reglas introduzca nuevos formularios del mismo ID. Por ejemplo, debe asegurarse de que ninguna regla de VISTA o de procesamiento introduce minúsculas en la prop o eVar solo en una parte de las visitas.
* La vinculación basada en campos no admite el uso de más de una prop o eVar con fines de vinculación. Por ejemplo, si eVar12 contiene el ID de inicio de sesión y eVar20 contiene el ID de correo electrónico, debe elegir uno de ellos.
* La vinculación basada en campos no combina ni concatena campos (por ejemplo, eVar10 + prop5).
* La prop o eVar deben contener un solo tipo de ID. Por ejemplo, la prop o eVar no debe contener una combinación de ID de inicio de sesión e ID de correo electrónico.
* Si se producen varias visitas con la misma marca de tiempo para el mismo visitante, pero con valores diferentes en la eVar o prop de vinculación, CDA elegirá en función del orden alfabético. Por lo tanto, si el visitante A tiene dos visitas con la misma marca de tiempo y una de las visitas especifica Bob y la otra especifica Ann, CDA elegirá Ann.


## Pasos siguientes

Una vez que su organización haya cumplido todos los requisitos y haya comprendido las limitaciones, puede empezar a [configurar Cross-Device Analytics](setup.md).
