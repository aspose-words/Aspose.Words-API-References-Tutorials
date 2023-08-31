---
title: Cambiar el nombre de los campos de combinación
linktitle: Cambiar el nombre de los campos de combinación
second_title: API de procesamiento de documentos Aspose.Words
description: En este tutorial, aprenderá cómo cambiar el nombre de los campos de combinación en un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/rename-merge-fields/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que utiliza la función de cambio de nombre de campos de combinación de Aspose.Words para .NET. Siga cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código proporcionado, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

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

## Paso 3: cambiar el nombre de los campos de combinación

Recorremos cada campo en el rango del documento y, si es un campo de combinación, cambiamos el nombre del campo agregando "_Sufijo "renombrado".

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

## Paso 4: guardar el documento

 Finalmente llamamos al`Save()` método para guardar el documento modificado.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Ejemplo de código fuente para cambiar el nombre de campos de combinación con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento e inserte los campos de combinación.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Cambie el nombre de los campos de combinación.
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

### Preguntas frecuentes

#### P: ¿Cómo puedo cambiar el nombre de los campos combinados en un documento de Word usando Aspose.Words para .NET?

 R: Para cambiar el nombre de los campos combinados en un documento de Word usando Aspose.Words para .NET, puede recorrer los campos en el documento usando el`FieldMergingArgs` clase y utilizar el`FieldMergingArgs.FieldName` método para cambiar el nombre del campo.

#### P: ¿Es posible cambiar el nombre sólo de ciertos campos combinados en un documento de Word con Aspose.Words para .NET?

R: Sí, es posible cambiar el nombre sólo de ciertos campos combinados en un documento de Word con Aspose.Words para .NET. Puede filtrar qué campos cambiar de nombre utilizando criterios específicos, como el nombre del campo u otras propiedades relevantes. Luego puede cambiar el nombre de los campos correspondientes usando el`FieldMergingArgs.FieldName` método.

#### P: ¿Cómo puedo comprobar si se cambió correctamente el nombre de un campo combinado en un documento de Word con Aspose.Words para .NET?

 R: Para comprobar si se cambió correctamente el nombre de un campo combinado en un documento de Word con Aspose.Words para .NET, puede utilizar el`FieldMergedArgs` clase y acceder a`FieldMergedArgs.IsMerged` propiedad para determinar si se cambió el nombre del campo con hit.

#### P: ¿Cuáles son las consecuencias de cambiar el nombre de un campo combinado en un documento de Word con Aspose.Words para .NET?

R: Cuando cambia el nombre de un campo combinado en un documento de Word con Aspose.Words para .NET, cambia el nombre del campo en el documento, lo que puede afectar otras funciones o procesos que dependen del nombre del campo. Asegúrese de considerar estas posibles consecuencias antes de cambiar el nombre de los campos combinados.

#### P: ¿Es posible restaurar el nombre original de un campo combinado después de cambiarle el nombre con Aspose.Words para .NET?

R: Sí, es posible restaurar el nombre original de un campo combinado después de cambiarle el nombre con Aspose.Words para .NET. Puede almacenar el nombre original del campo en una variable o lista y luego usar esa información para restaurar el nombre original si es necesario.