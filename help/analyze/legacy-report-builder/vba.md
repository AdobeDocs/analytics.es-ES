---
title: Cómo utilizar macros de Visual Basic en Report Builder
description: Obtenga información sobre cómo expandir la funcionalidad de los libros de Excel y Report Builder mediante macros de VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
TQID: https://experienceleague.adobe.com/RxOpojtJn2vi5uMO8CGzCCm7FcPp4qVwbH-XTEBSRsY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 64%

---

# Macros de Visual Basic en Report Builder

{{legacy-arb}}

Las macros de Visual Basic (VBA) proporcionan características que ayudan a actualizar los libros de Excel. Visual Basic tiene acceso al libro, Excel y Windows.

Debe ejecutar la versión más reciente de Report Builder e iniciar sesión antes de ejecutar macros de VBA.

>[!IMPORTANT]
>
>Por motivos de seguridad, no se puede programar un libro que contenga una macro.

Adobe admite tres métodos de API de Report Builder.

## `RefreshAllReportBuilderRequests()`

La macro `RefreshAllReportBuilderRequests()` actualiza todas las solicitudes del Report Builder del libro activo. Se inicia llamando al complemento COM del Report Builder a través de su ID de producto y, a continuación, llama al comando API `RefreshAllRequests()`:

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

La macro `RefreshAllReportBuilderRequestsInActiveWorksheet()` actualiza todas las solicitudes del Report Builder de la hoja de cálculo activa. La llamada de API `RefreshWorksheetRequests()` toma un objeto de hoja de cálculo como argumento. Puede utilizar esta llamada para cualquier hoja de cálculo que contenga solicitudes de Report Builder:

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

La macro `RefreshAllReportBuilderRequestsInCellsRange()` actualiza todas las solicitudes del Report Builder cuyas salidas de celda forman intersecciones con un intervalo de celdas específico. El rango de celdas utilizado en este ejemplo apunta al rango `B1:B54` de la hoja de cálculo “Datos” dentro del libro activo. La expresión de rango admite todas las expresiones de rango de Excel admitidas:

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
