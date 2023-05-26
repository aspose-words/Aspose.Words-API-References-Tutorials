---
title: Insertar campo Ninguno
linktitle: Insertar campo Ninguno
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a Insérez un champ AUCUN dans vos documentos Word con Aspose.Words pour .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field-none/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Insertar campo NINGUNO" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

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

## Paso 3: Inserción del campo NINGUNO

 usamos el`InsertField()` del DocumentBuilder para insertar un campo NINGUNO en el documento.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### Ejemplo de código fuente para insertar un campo NINGUNO con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte el campo NINGUNO.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

En este ejemplo, creamos un nuevo documento, inicializamos un DocumentBuilder y luego insertamos un campo NINGUNO. A continuación, el documento se guarda con un nombre de archivo especificado.

Esto concluye nuestra guía sobre el uso de la función "Insertar NINGUNO de los campos" con Aspose.Words para .NET.