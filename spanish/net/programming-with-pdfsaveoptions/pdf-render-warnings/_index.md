---
title: Advertencias de procesamiento de PDF
linktitle: Advertencias de procesamiento de PDF
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para lidiar con las advertencias de procesamiento de PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de advertencias de representación de PDF con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo lidiar con las advertencias de representación al convertir a PDF.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "WMF con imagen.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Paso 3: configure las opciones de guardar como PDF con advertencias de representación

Para manejar las advertencias de representación al convertir a PDF, necesitamos configurar el`MetafileRenderingOptions` object para especificar cómo se representan los metarchivos. También usamos el`HandleDocumentWarnings` opción para manejar las advertencias generadas al guardar el documento.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Paso 4: Guarde el documento como PDF con advertencias de representación

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Paso 5: manejar las advertencias de representación

Las advertencias de representación generadas al guardar el documento se pueden recuperar mediante el controlador de advertencia personalizado. En este ejemplo, simplemente imprimimos la descripción de cada advertencia.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

Eso es todo ! Ha manejado con éxito las advertencias de representación al convertir un documento

  a PDF usando Aspose.Words para .NET.

### Ejemplo de código fuente para las advertencias de representación de PDF con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// Si Aspose.Words no puede representar correctamente algunos de los registros del metarchivo
	// a gráficos vectoriales, Aspose.Words convierte este metarchivo en un mapa de bits.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Si bien el archivo se guarda correctamente, aquí se recopilan las advertencias de representación que ocurrieron durante el guardado.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```
