---
title: Establecer opciones de contorno
linktitle: Establecer opciones de contorno
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para establecer opciones de esquema en un documento PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/set-outline-options/
---

Este artículo proporciona una guía paso a paso sobre cómo usar las opciones de configuración de esquema para la función de tamaño de metarchivo con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo configurar las opciones de esquema en un documento y generar un PDF con las opciones de esquema correspondientes.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Rendering.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Configure las opciones de guardar como PDF con las opciones del plan

 Para establecer las opciones de esquema en el PDF generado, necesitamos configurar el`PdfSaveOptions` objeto. Podemos establecer el número de niveles de contorno de encabezado (`HeadingsOutlineLevels`) y el número de niveles de esquema expandido (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Paso 4: Guarde el documento como PDF con opciones de esquema

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Eso es todo ! Configuró con éxito las opciones de esquema en un documento y generó un PDF con las opciones de esquema correspondientes utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para configurar las opciones del plan al tamaño del metarchivo con Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```
