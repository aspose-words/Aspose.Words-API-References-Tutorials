---
title: Cultura de actualización de campo
linktitle: Cultura de actualización de campo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a actualizar la cultura de campo en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/field-update-culture/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la función "Actualización de cultura de campo" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear el documento y el generador de documentos

Comenzamos creando un nuevo documento y un generador de documentos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar el campo de tiempo

 usamos el`InsertField()` para insertar un campo de tiempo en el documento.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Esto insertará un campo de tiempo en el documento.

## Paso 4: Configuración de la cultura de actualización de campo

Configuramos las opciones de campo para especificar que la cultura de actualización de campo debe basarse en el código de campo.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Estas opciones determinan la referencia cultural utilizada para actualizar campos.

### Ejemplo de código fuente para actualizar Field Culture con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el generador de documentos.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte el campo de tiempo.
builder. InsertField(FieldType.FieldTime, true);

// Configure la referencia cultural de actualización de campo.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Guarde el documento.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo de tiempo y configuramos la referencia cultural de actualización de campo. Luego guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre el uso de la función "Actualizar cultura de campo" con Aspose.Words para .NET.