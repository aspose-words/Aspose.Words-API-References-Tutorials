---
title: Cambiar el nombre de los campos de combinación
linktitle: Cambiar el nombre de los campos de combinación
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenderá a cambiar el nombre de los campos de combinación en un documento utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/rename-merge-fields/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función de cambio de nombre de campo de combinación de Aspose.Words para .NET. Siga cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear el documento e insertar los campos de combinación

 Comenzamos creando un nuevo documento y usando un`DocumentBuilder` para insertar los campos de combinación.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Paso 3: Cambiar el nombre de los campos de combinación

Recorremos cada campo en el rango del documento, y si es un campo de combinación, cambiamos el nombre del campo agregando el "_Sufijo renombrado".

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Paso 4: Guardar el documento

 Finalmente, llamamos a la`Save()` para guardar el documento modificado.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Ejemplo de código fuente para cambiar el nombre de los campos de combinación con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento e inserte los campos de combinación.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Cambiar el nombre de los campos de combinación.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Guarde el documento.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Siga estos pasos para cambiar el nombre de los campos de combinación en su documento usando Aspose.Words para .NET.