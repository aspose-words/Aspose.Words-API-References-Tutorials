---
title: Escalar fuentes Wmf al tamaño de metarchivo
linktitle: Escalar fuentes Wmf al tamaño de metarchivo
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para ajustar el tamaño de fuente WMF al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la función Escalado de fuentes WMF a tamaño de metarchivo con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo habilitar o deshabilitar el escalado de fuentes WMF al convertir a PDF.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "WMF con texto.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Paso 3: Configure las opciones de representación de metarchivos

 Para habilitar o deshabilitar la escala de fuentes WMF al tamaño del metarchivo, debemos configurar el`MetafileRenderingOptions` objeto. En este ejemplo, deshabilitamos la escala de fuente configurando el`ScaleWmfFontsToMetafileSize` propiedad a`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Paso 4: configure las opciones de guardar como PDF con opciones de representación de metarchivos

Finalmente, podemos configurar las opciones de guardar en PDF utilizando las opciones de representación de metarchivos configuradas anteriormente.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Paso 5: Guarde el documento como PDF con opciones de representación de metarchivo

Guarde el documento en formato PDF utilizando las opciones de guardado previamente configuradas.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Eso es todo ! Ha habilitado o deshabilitado con éxito la escala de fuentes WMF al tamaño del metarchivo al convertir

un documento PDF utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para escalar fuentes WMF al tamaño de un metarchivo con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Si Aspose.Words no puede representar correctamente algunos de los registros del metarchivo en gráficos vectoriales
	// luego, Aspose.Words convierte este metarchivo en un mapa de bits.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```
