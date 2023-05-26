---
title: Especificar configuración regional a nivel de campo
linktitle: Especificar configuración regional a nivel de campo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a especificar la localización a nivel de campo en documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/specify-locale-at-field-level/
---

Aquí hay una guía paso a paso para explicar el siguiente código fuente de C# que permite especificar la localización a nivel de campo usando la función Aspose.Words para .NET. Asegúrese de haber incluido la biblioteca Aspose.Words en su proyecto antes de usar este código.

## Paso 1: establecer la ruta del directorio del documento

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Asegúrese de especificar la ruta correcta a su directorio de documentos donde se guardará el documento editado.

## Paso 2: Crear un generador de documentos

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Aquí estamos creando una instancia de la`DocumentBuilder` class que nos permitirá agregar campos al documento.

## Paso 3: inserte un campo de fecha con una ubicación específica

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Usamos el generador de documentos para insertar un campo de tipo`FieldType.FieldDate` en el documento. Al establecer el`LocaleId` propiedad a`1049`, especificamos la localización rusa para este campo.

## Paso 4: Guarde el documento modificado

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Finalmente, guardamos el documento modificado con la ubicación especificada en un archivo especificado.

### Ejemplo de código fuente para especificar la localización a nivel de campo con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Este fue un código fuente de ejemplo para especificar la localización a nivel de campo en un documento usando Aspose.Words para .NET. Puede usar este código para insertar campos de fecha con ubicaciones específicas en sus documentos de Word.
