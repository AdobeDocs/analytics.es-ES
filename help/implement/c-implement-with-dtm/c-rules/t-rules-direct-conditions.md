---
description: Creación de condiciones para reglas de llamada directa.
keywords: Dynamic Tag Management;regla;crear regla;nueva regla;regla de llamada directa
seo-description: Creación de condiciones para reglas de llamada directa.
seo-title: Creación de condiciones para reglas de llamada directa
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Creación de condiciones para reglas de llamada directa
uuid: bab0e058-a5b8-4039-8333-5e8f3d06ade4
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Creación de condiciones para reglas de llamada directa

Creación de condiciones para reglas de llamada directa.

1. En el diálogo **[!UICONTROL Condiciones]**, especifique la cadena que se transmitirá a `_satellite.track()` en la llamada directa, sin comillas.

   ![](assets/conditions-direct-call.png)

   >[!NOTE]
   >
   >Si especifica la cadena que pasará a `_satellite.track()` en una llamada directa a través de la interfaz de usuario, tal y como hemos descrito, no utilice comillas. Si inserta un [código de página personalizado](../../../implement/c-implement-with-dtm/c-aa-tool/customize-page-code.md#concept_7D6390823DFE4D29AF9505CCE1A79C3B) mediante el editor, debe usar comillas.

