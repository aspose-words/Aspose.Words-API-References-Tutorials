---
title: Tipo de control preferido en documento de Word
linktitle: Tipo de control preferido en documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para especificar el tipo de control preferido en un documento de Word al cargar un documento HTML con Aspose.Words para .NET.
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

 usamos el`Document` class para cargar código HTML desde un flujo de memoria con las opciones de carga definidas anteriormente. Luego guardamos el documento en el directorio especificado con el`.docx`formato de archivo.

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

## Conclusión

 Al seguir esta guía paso a paso, ha aprendido a usar la función "Tipo de control preferido" en Aspose.Words para .NET para especificar el tipo de control deseado al cargar un documento HTML. Configuración de la`PreferredControlType` propiedad a`HtmlControlType.StructuredDocumentTag` permite que Aspose.Words use etiquetas de documentos estructurados (SDT) para una mejor representación y procesamiento del contenido HTML. También puede explorar otros tipos de control para satisfacer sus requisitos específicos. El uso de esta función ayuda a garantizar un manejo preciso y eficiente de documentos HTML en su aplicación C# con Aspose.Words.

### Preguntas frecuentes sobre el tipo de control preferido en un documento de Word

#### P: ¿Qué es la función "Tipo de control preferido" en Aspose.Words para .NET?

R: La función "Tipo de control preferido" le permite especificar el tipo de control preferido para representar elementos HTML al cargar un documento HTML. Ayuda a seleccionar el tipo de control apropiado para una mejor representación y procesamiento del contenido HTML.

#### P: ¿Cómo configuro el tipo de control preferido al cargar un documento HTML?

 R: Para establecer el tipo de control preferido, debe crear un`HtmlLoadOptions` objeto y establecer su`PreferredControlType` propiedad a la deseada`HtmlControlType` . En el ejemplo proporcionado,`HtmlControlType.StructuredDocumentTag` se usa

#### P: ¿Cuál es la importancia de usar etiquetas de documentos estructurados (SDT) como el tipo de control preferido?

R: Las etiquetas de documentos estructurados (SDT) son elementos basados en XML que se pueden usar para representar contenido y controles complejos en un documento de Word. El uso de SDT como tipo de control preferido puede proporcionar una mejor compatibilidad y representación del contenido HTML.

#### P: ¿Cómo puedo asegurarme de que Aspose.Words utilice el tipo de control preferido al cargar el documento HTML?

 R: Al configurar el`PreferredControlType` propiedad a`HtmlControlType.StructuredDocumentTag`como se muestra en el código fuente de ejemplo, Aspose.Words usará SDT para representar elementos HTML al cargar el documento.

#### P: ¿Puedo usar otros tipos de control como opción preferida?

 R: Sí, aparte de`HtmlControlType.StructuredDocumentTag` , Aspose.Words para .NET admite otros tipos de control como`HtmlControlType.ContentControl` y`HtmlControlType.CustomXmlMarkup`.