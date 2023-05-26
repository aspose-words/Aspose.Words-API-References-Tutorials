---
title: Tipo de control preferido
linktitle: Tipo de control preferido
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para especificar el tipo de control preferido al cargar un documento HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlloadoptions/preferred-control-type/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de tipo de control preferido con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo especificar el tipo de control preferido al cargar un documento HTML.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el código HTML

 Para comenzar, debe definir el código HTML que desea cargar como documento. En este ejemplo, hemos definido un`html` variable que contiene el código HTML de un selector con opciones.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Paso 2: establece las opciones de carga de HTML

 A continuación, creamos un`HtmlLoadOptions` objeto y establecer el`PreferredControlType` propiedad a`HtmlControlType.StructuredDocumentTag`. Esto le dice a Aspose.Words que use etiquetas de documentos estructurados para representar HTML al cargar.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Paso 3: Cargue y guarde el documento

 usamos el`Document` class para cargar código HTML desde un flujo de memoria con las opciones de carga definidas anteriormente. Luego guardamos el documento en el directorio especificado con el`.docx` formato de archivo.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Ejemplo de código fuente para el tipo de control preferido con Aspose.Words para .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Eso es todo ! Ha especificado correctamente el tipo de control preferido al cargar un documento HTML con Aspose.Words para .NET.