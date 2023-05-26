---
title: Eliminar campo
linktitle: Eliminar campo
second_title: Referencia de API de Aspose.Words para .NET
description: En esta guía, aprenderá a eliminar un campo específico en un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/remove-field/
---
Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la funcionalidad "Eliminación de campo" de Aspose.Words para .NET. Siga cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargar el documento

Comenzamos cargando el documento existente desde el archivo especificado.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## Paso 3: Eliminar el campo

 Seleccionamos el primer campo en el rango del documento y usamos el`Remove()` método para eliminarlo.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## Paso 4: Guardar el documento

 Finalmente, llamamos a la`Save()` para guardar el documento modificado.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### Ejemplo de código fuente para la eliminación de campos con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento.
Document doc = new Document(dataDir + "Various fields.docx");

// Selección del campo a borrar.
Field field = doc.Range.Fields[0];
field. Remove();

// Guarde el documento.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

Siga estos pasos para eliminar un campo específico en su documento usando Aspose.Words para .NET.
