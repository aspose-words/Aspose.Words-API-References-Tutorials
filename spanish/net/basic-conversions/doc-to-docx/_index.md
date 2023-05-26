---
title: De documento a documento
linktitle: De documento a documento
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos de Word de formato .doc a Docx usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/doc-to-docx/
---

En este tutorial, lo guiaremos paso a paso a través del proceso de uso de Aspose.Words para .NET para convertir un documento de Word en formato .doc al formato Docx. Explicaremos el código fuente de C# provisto y lo guiaremos sobre cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: Configuración del entorno de desarrollo

Antes de comenzar a codificar, asegúrese de tener un entorno de desarrollo adecuado. Abra Visual Studio o su C# IDE preferido y cree un nuevo proyecto.

## Paso 2: agregar referencias e importar espacios de nombres

Para usar Aspose.Words para .NET, debe agregar referencias a la biblioteca en su proyecto. Haga clic con el botón derecho en la carpeta Referencias de su proyecto, seleccione "Agregar referencia" y busque la ubicación donde instaló la biblioteca Aspose.Words para .NET. Seleccione la versión adecuada y haga clic en "Aceptar" para agregar la referencia.

A continuación, importe los espacios de nombres necesarios en la parte superior de su archivo C#:

```csharp
using Aspose.Words;
```

## Paso 3: inicialización del objeto de documento

 En este paso, inicializará el`Document` objeto con la ruta a su documento de origen en formato .doc. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta del directorio real donde se encuentra su documento, y`"Document.doc"` con el nombre de su documento fuente. Aquí está el fragmento de código:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## Paso 4: Conversión del documento a formato Docx

 Ahora que ha inicializado el`Document`objeto, puede continuar con el proceso de conversión. Aspose.Words para .NET proporciona varias opciones y configuraciones para la personalización, pero para una conversión básica, no se requieren parámetros adicionales.

## Paso 5: guardar el documento convertido

 Para guardar el documento convertido en formato Docx, debe llamar al`Save` método en el`Document` objeto. Proporcione la ruta y el nombre de archivo del documento de salida. En este ejemplo, lo guardaremos como`"BaseConversions.DocToDocx.docx"`. Aquí está el fragmento de código:

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato .doc al formato Docx utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para Doc To Docx usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.




