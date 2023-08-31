---
title: Establecer ruso como idioma de edición predeterminado
linktitle: Establecer ruso como idioma de edición predeterminado
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar el ruso como idioma de edición predeterminado de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar el ruso como idioma de edición predeterminado con Aspose.Words para .NET. Esta función le permite configurar el idioma predeterminado al cargar un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word para el que queremos configurar el ruso como idioma de edición predeterminado. Utilice el siguiente código para cargar el documento:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: comprobar el idioma predeterminado

Después de cargar el documento, comprobaremos si el idioma predeterminado se ha configurado correctamente en ruso. Utilice el siguiente código para obtener el ID de idioma predeterminado:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

El código comprueba si el ID del idioma coincide con el del ruso. Según el resultado, muestra el mensaje correspondiente.

### Código fuente de ejemplo para establecer el ruso como idioma de edición predeterminado usando Aspose.Words para .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo configurar el ruso como idioma de edición predeterminado para un documento usando Aspose.Words para .NET. Siguiendo la guía de pasos