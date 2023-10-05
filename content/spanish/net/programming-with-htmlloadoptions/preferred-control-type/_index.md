---
title: Tipo de control preferido en documento de Word
linktitle: Tipo de control preferido en documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para especificar el tipo de control preferido en un documento de Word al cargar un documento HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlloadoptions/preferred-control-type/
---
Este artículo proporciona una guía paso a paso sobre cómo utilizar la función de tipo de control preferido con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo especificar el tipo de control preferido al cargar un documento HTML.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: definir el código HTML

 Para comenzar, debe definir el código HTML que desea cargar como documento. En este ejemplo, hemos definido un`html` Variable que contiene el código HTML de un selector con opciones.

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

## Paso 2: configurar las opciones de carga HTML

 A continuación, creamos un`HtmlLoadOptions` objeto y establecer el`PreferredControlType`propiedad a`HtmlControlType.StructuredDocumentTag`. Esto le indica a Aspose.Words que use StructuredDocumentTags para representar HTML al cargar.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Paso 3: Cargue y guarde el documento

 Usamos el`Document` clase para cargar código HTML desde una secuencia de memoria con las opciones de carga definidas anteriormente. Luego guardamos el documento en el directorio especificado con el`.docx`formato de archivo.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Código fuente de ejemplo para el tipo de control preferido con Aspose.Words para .NET

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

 Siguiendo esta guía paso a paso, habrá aprendido cómo utilizar la función "Tipo de control preferido" en Aspose.Words para .NET para especificar el tipo de control deseado al cargar un documento HTML. Configurando el`PreferredControlType`propiedad a`HtmlControlType.StructuredDocumentTag` permite a Aspose.Words utilizar StructuredDocumentTags (SDT) para una mejor representación y procesamiento del contenido HTML. También puede explorar otros tipos de control que se adapten a sus necesidades específicas. El uso de esta característica ayuda a garantizar un manejo preciso y eficiente de documentos HTML en su aplicación C# con Aspose.Words.

### Preguntas frecuentes sobre el tipo de control preferido en un documento de Word

#### P: ¿Qué es la función "Tipo de control preferido" en Aspose.Words para .NET?

R: La función "Tipo de control preferido" le permite especificar el tipo de control preferido para representar elementos HTML al cargar un documento HTML. Ayuda a seleccionar el tipo de control apropiado para una mejor representación y procesamiento del contenido HTML.

#### P: ¿Cómo configuro el tipo de control preferido al cargar un documento HTML?

 R: Para establecer el tipo de control preferido, debe crear un`HtmlLoadOptions` objeto y establecer su`PreferredControlType` propiedad a la deseada`HtmlControlType` . En el ejemplo proporcionado,`HtmlControlType.StructuredDocumentTag` se utiliza.

#### P: ¿Cuál es la importancia de utilizar StructuredDocumentTags (SDT) como tipo de control preferido?

R: StructuredDocumentTags (SDT) son elementos basados en XML que se pueden utilizar para representar contenido y controles complejos en un documento de Word. El uso de SDT como tipo de control preferido puede proporcionar una mejor compatibilidad y representación del contenido HTML.

#### P: ¿Cómo puedo asegurarme de que Aspose.Words utilice el tipo de control preferido al cargar el documento HTML?

 R: Al configurar el`PreferredControlType`propiedad a`HtmlControlType.StructuredDocumentTag`como se muestra en el código fuente de ejemplo, Aspose.Words utilizará SDT para representar elementos HTML al cargar el documento.

#### P: ¿Puedo utilizar otros tipos de control como opción preferida?

 R: Sí, aparte de`HtmlControlType.StructuredDocumentTag` , Aspose.Words para .NET admite otros tipos de control como`HtmlControlType.ContentControl` y`HtmlControlType.CustomXmlMarkup`.