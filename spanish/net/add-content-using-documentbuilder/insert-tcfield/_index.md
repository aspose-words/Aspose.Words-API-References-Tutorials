---
title: Insertar campo TC
linktitle: Insertar campo TC
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar y manipular TCFields en documentos de Word usando C# y Aspose.Words para .NET en esta guía paso a paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-tcfield/
---

En este ejemplo, lo guiaremos a través del proceso de uso de la función Insertar TCField de Aspose.Words para .NET. El TCField representa una entrada de tabla de contenido en un documento de Word. Proporcionaremos una explicación paso a paso del código fuente de C#, junto con el resultado esperado en formato de descuento. ¡Empecemos!

## Paso 1: Inicializar el documento y el generador de documentos

Para comenzar, necesitamos inicializar el documento y el generador de documentos. El generador de documentos es una poderosa herramienta proporcionada por Aspose.Words para .NET que nos permite construir y manipular documentos de Word mediante programación. Así es como puedes hacerlo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Insertar el TCField

 A continuación, insertaremos el TCField en el documento usando el`InsertField` método. El TCField representa una entrada de tabla de contenido con el texto de entrada especificado. Aquí hay un ejemplo:

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

El código anterior insertará un TCField con el texto de entrada "Texto de entrada" en el documento.

## Paso 3: Guardar el documento

 Después de insertar el TCField, podemos guardar el documento en una ubicación específica usando el`Save` método. Asegúrese de proporcionar la ruta y el nombre de archivo deseados para el documento de salida. Aquí hay un ejemplo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

El código anterior guardará el documento con TCField en el directorio especificado.

## Formatos de descuento de salida

Cuando el código se ejecuta con éxito, el documento de salida contendrá una entrada de tabla de contenido con el texto de entrada especificado. El TCField se representa como un campo en el documento de Word y el formato de descuento resultante dependerá de cómo se procese el documento.

Tenga en cuenta que el documento de salida no está directamente en formato Markdown sino en formato Word. Sin embargo, cuando convierte el documento de Word a Markdown utilizando las herramientas o bibliotecas adecuadas, el TCField se procesará en consecuencia.

### Ejemplo de código fuente para insertar TCField usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para insertar un TCField usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertField("TC \"Entry Text\" \\f t");

	doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
			
```

Siéntase libre de modificar el código de acuerdo con sus requisitos y explorar otras funciones proporcionadas por Aspose.Words para .NET.

¡Eso es todo! Ha aprendido con éxito cómo insertar un TCField utilizando Aspose.Words para .NET.

