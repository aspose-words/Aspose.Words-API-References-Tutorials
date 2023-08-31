---
title: Lista Mantener formato de origen
linktitle: Lista Mantener formato de origen
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a conservar el formato de la lista mientras une y agrega documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/list-keep-source-formatting/
---

Este tutorial lo guiará a través del proceso de uso de la función de formato de fuente de mantenimiento de lista de Aspose.Words para .NET. Esta función le permite unir y agregar documentos de Word mientras conserva el formato de origen de las listas.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicialice los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir`variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue los documentos de origen y destino

 A continuación, debe cargar los documentos de origen y destino utilizando Aspose.Words`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Paso 3: configure el documento de origen para que fluya continuamente

 Para asegurarse de que el contenido del documento de origen fluya continuamente cuando se agregue al documento de destino, debe configurar el`SectionStart` propiedad de la primera sección en el documento fuente para`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Paso 4: agregue el documento de origen al documento de destino

 Ahora, puede agregar el documento de origen al documento de destino usando el`AppendDocument` metodo de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen, incluido el formato de las listas, se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: Guarde el documento final

 Por último, guarde el documento fusionado con la función Lista Mantener formato de origen habilitada mediante el`Save` metodo de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Ejemplo de código fuente para el formato de fuente de mantenimiento de lista usando Aspose.Words para .NET 

Aquí está el código fuente completo para la característica Lista Mantener formato de fuente en C# usando Aspose.Words para .NET:

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Agregue el contenido del documento para que fluya continuamente.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

¡Eso es todo! Ha implementado con éxito la función de formato de fuente de mantenimiento de lista mediante Aspose.Words para .NET. El documento final contendrá el contenido combinado con el formato de lista del documento de origen conservado.