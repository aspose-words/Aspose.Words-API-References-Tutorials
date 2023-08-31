---
title: Exportar URL de Cid para recursos Mhtml
linktitle: Exportar URL de Cid para recursos Mhtml
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para exportar URL CID de recursos MHTML al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

En este tutorial, lo guiaremos a través del código fuente de C# para exportar URL de CID para recursos MHTML con Aspose.Words para .NET. Esta función le permite exportar URL CID de recursos MHTML al guardar un documento en formato MHTML.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento a exportar. Utilice el siguiente código para cargar el documento desde un directorio específico:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Este código crea una instancia de`Document` cargando el documento desde el directorio especificado.

## Paso 3: configurar las opciones de copia de seguridad HTML

Ahora configuraremos las opciones de guardado de HTML para exportar URL CID de recursos MHTML. Utilice el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Este código crea una instancia de`HtmlSaveOptions` con el formato de guardado establecido en MHTML. También permite la exportación de URL CID de recursos MHTML configurando`ExportCidUrlsForMhtmlResources` a`true`.

## Paso 4: convertir y guardar el documento a MHTML

Finalmente, convertiremos el documento a MHTML usando las opciones de guardado de HTML configuradas anteriormente. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Este código convierte el documento a MHTML y lo guarda en un archivo con las URL CID de los recursos MHTML exportados.

### Código fuente de ejemplo para exportar URL de Cid para recursos Mhtml usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.

Ahora ha aprendido cómo exportar URL CID de recursos MHTML al guardar un documento en formato MHTML usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, puede administrar fácilmente las URL de CID en sus documentos MHTML exportados.

