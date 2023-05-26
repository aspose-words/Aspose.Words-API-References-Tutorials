---
title: Insertar campo avanzado sin generador de documentos
linktitle: Insertar campo avanzado sin generador de documentos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un campo avanzado en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Inserción de campo avanzada sin DocumentBuilder" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Creando el Documento y el Párrafo

Comenzamos creando un nuevo documento y recuperando el primer párrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Paso 3: Insertar el campo avanzado

 usamos el`AppendField()`para insertar un campo avanzado en el párrafo.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Luego configuramos las diversas propiedades del campo avanzado especificando los valores deseados.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo de código fuente para insertar un campo avanzado sin DocumentBuilder con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserte el campo avanzado.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo avanzado sin usar DocumentBuilder, configuramos varias propiedades de campo y guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre cómo usar la función "Insertar campo avanzado sin DocumentBuilder" con Aspose.Words para .NET.

