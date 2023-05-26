---
title: Exportar campo de formulario de entrada de texto como texto
linktitle: Exportar campo de formulario de entrada de texto como texto
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para exportar campos de formulario de entrada de texto como texto sin formato con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

En este tutorial, lo guiaremos a través del código fuente de C# para exportar campos de formulario de entrada de texto como texto sin formato con Aspose.Words para .NET. Esta función le permite exportar campos de formulario de entrada de texto como texto legible, en lugar de exportarlos como elementos de entrada HTML.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso cargaremos el documento a exportar. Use el siguiente código para cargar el documento desde un directorio específico:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Este código crea una instancia de`Document` cargando el documento desde el directorio especificado.

## Paso 3: Configuración de las opciones de copia de seguridad de HTML

Ahora configuraremos las opciones de guardado de HTML para exportar campos de formulario de entrada de texto como texto sin formato. Usa el siguiente código:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// La carpeta especificada debe existir y estar vacía.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Este código crea una instancia de`HtmlSaveOptions` establece el`ExportTextInputFormFieldAsText` opción a`true`para exportar campos de formulario de entrada de texto como texto sin formato. Además, especifica la carpeta donde se guardarán las imágenes extraídas.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML utilizando las opciones de guardado de HTML configuradas anteriormente. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Este código convierte el documento a HTML mediante la exportación de campos de formulario de entrada de texto como texto sin formato y guarda el archivo HTML exportado en el directorio especificado.

### Ejemplo de código fuente para Exportar campo de formulario de entrada de texto como texto usando Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// La carpeta especificada debe existir y debe estar vacía.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Establezca una opción para exportar campos de formulario como texto sin formato, no como elementos de entrada HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.