---
title: Crear nuevo documento
linktitle: Crear nuevo documento
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda cómo crear un nuevo documento de Word y agregar contenido usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/create-new-document/
---

En este tutorial paso a paso, aprenderá cómo crear un nuevo documento de Word desde cero usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá generar un nuevo documento y agregarle contenido utilizando la clase DocumentBuilder.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Crear un nuevo documento
Para comenzar, crea un nuevo documento usando la clase Document:

```csharp
Document doc = new Document();
```

## Paso 2: agregar contenido al documento
A continuación, utilice un objeto DocumentBuilder para agregar contenido al documento. Inicialice DocumentBuilder con el documento recién creado:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## Paso 3: Guarde el documento
Después de agregar el contenido deseado, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Ejemplo de código fuente para crear un nuevo documento usando Aspose.Words para .NET
Aquí está el código fuente completo para crear un nuevo documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document();

// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo crear un nuevo documento de Word utilizando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente provisto, ahora puede generar nuevos documentos mediante programación y agregarles contenido usando la clase DocumentBuilder.

Ahora puede crear y personalizar con confianza documentos de Word de acuerdo con sus requisitos específicos.

### Ejemplo de código fuente para crear un nuevo documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document();

// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

Recuerde ajustar la ruta y el nombre del archivo en el código para guardar el documento en la ubicación deseada en su sistema.

