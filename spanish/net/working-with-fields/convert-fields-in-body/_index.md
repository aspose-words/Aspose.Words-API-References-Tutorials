---
title: Convertir campos en el cuerpo
linktitle: Convertir campos en el cuerpo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar Aspose.Words para .NET para convertir campos de página en texto en el cuerpo de un documento de Word.
type: docs
weight: 10
url: /es/net/working-with-fields/convert-fields-in-body/
---

En este tutorial paso a paso, lo guiaremos a través de cómo usar la función ConvertFieldsInBody de Aspose.Words para .NET usando el código fuente de C# provisto. Esta función le permite convertir campos específicos en el cuerpo de su documento a texto sin formato, lo que facilita el procesamiento de sus documentos. Siga los pasos a continuación para usar esta función de manera efectiva.

## Paso 1: Requisitos previos

Antes de comenzar, asegúrese de haber instalado Aspose.Words para .NET y tener un documento listo para procesar. También asegúrese de tener la ruta del directorio a sus documentos.

## Paso 2: Cargue el documento

Comience declarando una variable para la ruta a su directorio de documentos, luego use esa variable para inicializar un objeto Documento desde el documento especificado. En nuestro ejemplo, el documento se llama "Campos vinculados.docx".

```csharp
// La ruta a su directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Cargue el documento
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Paso 3: Convierta los campos de página en texto sin formato

Ahora que el documento está cargado, podemos pasar a los pasos de conversión. Para convertir los campos de la página en texto sin formato en el cuerpo de la primera sección, puede utilizar el`Range.Fields` método para obtener todos los campos en el rango especificado y luego filtrar los campos de tipo`FieldType.FieldPage` . Entonces puedes usar el`ForEach` método para recorrer cada campo y llamar al`Unlink()` método para convertirlo a texto sin formato.

```csharp
// Pase los parámetros adecuados para convertir los campos de la página en texto sin formato en el cuerpo de la primera sección.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Paso 4: Guarde el documento modificado

 Una vez que haya convertido los campos de la página a texto sin formato, puede guardar el documento modificado usando el`Save()` y especificando la ruta y el nombre del archivo de salida. En nuestro ejemplo, lo guardamos como "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Ejemplo de código fuente para convertir campos en el cuerpo con Aspose.Words para .NET

Aquí está el ejemplo de código fuente completo para convertir campos en el cuerpo usando Aspose.Words para .NET:

```csharp
// La ruta a su directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Cargue el documento
Document doc = new Document(dataDir + "Linked fields.docx");

// Pase los parámetros adecuados para convertir los campos de la página en texto sin formato en el cuerpo de la primera sección.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```