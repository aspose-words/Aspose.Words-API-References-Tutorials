---
title: Convertir campos en párrafo
linktitle: Convertir campos en párrafo
second_title: Referencia de API de Aspose.Words para .NET
description: Convierta los campos IF en texto sin formato en un párrafo con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/convert-fields-in-paragraph/
---

Aquí hay un tutorial que demuestra cómo usar la función Convertir campos en párrafo con Aspose.Words para .NET. Este código convierte todos los campos de tipo IF que se encuentran en el último párrafo de un documento en texto sin formato. Siga los pasos a continuación para comprender y ejecutar este código.

Asegúrese de haber instalado Aspose.Words para .NET y configure su entorno de desarrollo antes de comenzar.

## Paso 1: Importar referencias

Para usar Aspose.Words en su proyecto, debe agregar las referencias necesarias. Asegúrese de haber agregado una referencia a la biblioteca Aspose.Words en su proyecto.

## Paso 2: Cargar el documento

Antes de poder convertir campos, debe cargar el documento que contiene los campos para convertir. Asegúrese de especificar la ruta correcta al directorio que contiene el documento. A continuación se explica cómo cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Convertir campos a texto

Ahora que el documento está cargado, podemos proceder a convertir los campos de tipo a texto sin formato. En este ejemplo, solo apuntamos a los campos presentes en el último párrafo del documento. Aquí está el código que realiza esta conversión:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Este código utiliza una combinación de métodos LINQ para filtrar campos en el último párrafo del documento y luego los convierte en texto sin formato llamando a la`Unlink()` método.

## Paso 4: Guardar el documento modificado

 Una vez convertidos los campos, puede guardar el documento modificado. Utilizar el`Save()` método para esto. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para la copia de seguridad.

### Ejemplo de código fuente para Convertir campos en párrafo usando Aspose.Words para .NET

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento.
Document doc = new Document(dataDir + "Linked fields.docx");

// Convierta los campos IF en texto sin formato en el último párrafo del documento.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Guarde el documento modificado.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```
