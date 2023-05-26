---
title: Exportación de propiedades personalizadas
linktitle: Exportación de propiedades personalizadas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a exportar propiedades personalizadas al convertir documentos a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/custom-properties-export/
---

En este tutorial, lo guiaremos a través de los pasos para exportar las propiedades personalizadas de un documento usando Aspose.Words para .NET. La exportación de propiedades personalizadas le permite incluir información adicional en el documento PDF generado. Siga los pasos a continuación:

## Paso 1: crear un documento y agregar propiedades personalizadas

Comience creando una instancia de la clase Documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Paso 2: Agregar propiedades personalizadas
 continuación, agregue las propiedades personalizadas deseadas. Por ejemplo, para agregar una propiedad "Empresa" con el valor "Aspose", use el`Add` método de la colección CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Puede agregar tantas propiedades personalizadas como sea necesario.

## Paso 3: Configure las opciones de exportación de PDF

Cree una instancia de la clase PdfSaveOptions y especifique cómo exportar propiedades personalizadas:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Esta opción controla la exportación de propiedades personalizadas al convertir a PDF.

## Paso 4: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Ejemplo de código fuente para la exportación de propiedades personalizadas mediante Aspose.Words para .NET

Aquí está el código fuente completo para exportar propiedades personalizadas desde un documento usando Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Siguiendo estos pasos, puede exportar fácilmente las propiedades personalizadas de un documento al convertirlo a PDF con Aspose.Words para .NET.

