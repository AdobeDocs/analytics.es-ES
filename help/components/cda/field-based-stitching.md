---
title: Vinculación basada en el campo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante la vinculación basada en el campo.
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
feature: CDA
role: Admin
TQID: 'https://experienceleague.adobe.com/OoJZJsKu6xV4OfPVZ-7Pqe8J8GfZu6AlgRrNl1GXR70'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: f99536a1-75c7-4151-a2c8-073630632526
    internal-label: CDA
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 81%
---
# Vinculación basada en el campo

{{available-existing-customers}}

Cross-Device Analytics proporciona dos métodos distintos para unir datos. Este método depende de una variable de Analytics, como una [propiedad](/help/implement/vars/page-vars/prop.md) o un [eVar](/help/implement/vars/page-vars/evar.md), para contener un identificador de persona. Utiliza esa variable como base para vincular dispositivos. Adobe recomienda esta opción de vinculación para lograr una mayor transparencia y previsibilidad en el seguimiento de visitantes.

## Requisitos previos específicos de la vinculación basada en el campo

Si tiene intención de implementar el análisis entre dispositivos mediante la vinculación basada en el campo, es necesario lo siguiente. Trabaje con equipos de su organización y con el equipo de cuenta de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!WARNING]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Todos los requisitos previos enumerados en la [página de información general](overview.md).
* La implementación debe establecer una propiedad o una eVar que identifique de forma exclusiva a un individuo siempre que sea posible, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan.<br/>Evite asignar un valor predeterminado a esta propiedad o eVar. Cuando se asignan el mismo valor predeterminado a 2000 dispositivos o más diferentes, la persona se agrega a una lista de &quot;personas malas&quot; y estos eventos se eliminan del grupo de informes virtuales habilitado para CDA, lo que da como resultado un análisis erróneo.
* Comunique la variable de identificación que desee al equipo de cuenta de Adobe cuando se aprovisione para la vinculación basada en el campo.

## Limitaciones específicas de la vinculación basada en el campo

* La vinculación basada en campos funciona mejor en los grupos de informes que tienen una alta tasa de identificación/autenticación de usuarios.
* Aunque las props y eVars tienen reglas para la administración de caracteres en mayúsculas y minúsculas destinadas a la creación de informes, la vinculación basada en el campo no transforma la prop o eVar que se usa para la vinculación de ninguna manera. La vinculación basada en campos utiliza el valor del campo especificado, ya que existe después de las reglas de VISTA y después de las reglas de procesamiento. El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, si en el campo unas veces aparece la palabra &quot;Bob&quot; y otras la palabra &quot;BOB&quot;, estas se tratarán como dos personas independientes en el proceso de vinculación.
* Dado que la vinculación basada en campos distingue entre mayúsculas y minúsculas, Adobe recomienda revisar las reglas de VISTA o de procesamiento que se apliquen a la prop o eVar que se esté utilizando para la vinculación basada en campos. Deben revisarse para garantizar que ninguna de estas reglas introduzca nuevos formularios del mismo ID. Por ejemplo, debe asegurarse de que ninguna regla de VISTA o de procesamiento introduce minúsculas en la prop o eVar solo en una parte de los hits.
* La vinculación basada en campos no admite el uso de más de una prop o eVar con fines de vinculación. Por ejemplo, si eVar12 contiene el ID de inicio de sesión y eVar20 contiene el ID de correo electrónico, debe elegir uno de ellos.
* La vinculación basada en campos no combina ni concatena campos (por ejemplo, eVar10 + prop5).
* La prop o eVar deben contener un solo tipo de ID. Por ejemplo, la prop o eVar no debe contener una combinación de ID de inicio de sesión e ID de correo electrónico.
* Si se producen varios hits con la misma marca de tiempo para el mismo visitante, pero con valores diferentes en la eVar o prop de vinculación, CDA elegirá en función del orden alfabético. Por lo tanto, si el visitante A tiene dos hits con la misma marca de tiempo y uno de los hits especifica Bob y el otra especifica Ann, CDA elegirá Ann.


## Pasos siguientes

Una vez que su organización haya cumplido todos los requisitos y haya comprendido las limitaciones, puede empezar a [configurar Cross-Device Analytics](setup.md).

