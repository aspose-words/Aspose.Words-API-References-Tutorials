---
title: Insertar campo
linktitle: Insertar campo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un campo en sus documentos de Word con Aspose.Words para .NET. Personaliza tus documentos con campos dinámicos.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la función "Insertar un campo" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear el Documento y DocumentBuilder

Comenzamos creando un nuevo documento e inicializando un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar el campo

 usamos el`InsertField()` del DocumentBuilder para insertar un campo en el documento. En este ejemplo, insertamos un campo de combinación (MERGEFIELD) con el nombre de campo "MyFieldName" y formato de combinación.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Ejemplo del código fuente para insertar un campo con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta el campo.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

En este ejemplo, creamos un nuevo documento, inicializamos un DocumentBuilder y luego insertamos un campo de combinación con el nombre de campo "MyFieldName" y el formato de combinación. A continuación, el documento se guarda con un nombre de archivo especificado.

Esto concluye nuestra guía sobre el uso de la función "Insertar un campo" con Aspose.Words para .NET.
