---
title: Insertar imagen en línea
linktitle: Insertar imagen en línea
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar imágenes en línea en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-inline-image/
---

En este completo tutorial, aprenderá a insertar imágenes en línea en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar imágenes directamente al texto de sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserte una imagen en línea
A continuación, utilice el método InsertImage de la clase DocumentBuilder para insertar una imagen en línea en el documento. Proporcione la ruta del archivo de imagen como parámetro:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Paso 3: Guarde el documento
Después de insertar la imagen en línea, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Ejemplo de código fuente para insertar imagen en línea usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar una imagen en línea usando Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar imágenes en línea en un documento de Word utilizando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente provisto, ahora puede agregar imágenes sin problemas dentro del texto de sus documentos.

Las imágenes en línea son útiles para varios escenarios, como agregar ilustraciones, logotipos u otros elementos visuales directamente en el flujo del documento.
