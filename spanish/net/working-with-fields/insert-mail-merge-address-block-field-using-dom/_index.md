---
title: Insertar campo de bloque de dirección de combinación de correspondencia usando DOM
linktitle: Insertar campo de bloque de dirección de combinación de correspondencia usando DOM
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un campo de bloque de dirección de combinación de correspondencia en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Insertar campo de bloque de dirección de combinación de correspondencia" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

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

## Paso 3: mover el cursor al párrafo

 Usamos el DocumentBuilder`MoveTo()` para mover el cursor al párrafo donde queremos insertar el campo de bloque de dirección de combinación de correspondencia.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Paso 4: Inserción del campo de bloque de dirección de combinación de correspondencia

 Usamos el DocumentBuilder`InsertField()` para insertar un campo de bloque de dirección de combinación de correspondencia en el párrafo.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Luego configuramos las propiedades del campo de bloque de direcciones especificando las opciones apropiadas, como incluir el nombre del país/región, formatear la dirección según el país/región, excluir los nombres de países/regiones, formato de nombre y dirección e identificador de idioma.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo de código fuente para insertar un campo de bloque de dirección de combinación de correspondencia con Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Queremos insertar un bloque de dirección de combinación de correspondencia como este:
// { BLOQUEDIRECCIÓN \\c 1 \\d \\e Prueba2 \\f Prueba3 \\l \"Prueba 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { BLOQUEDIRECCIONES \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { BLOQUEDIRECCIONES \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { BLOQUEDIRECCIONES \\c 1 \\d \\e Prueba2 }
field.ExcludedCountryOrRegionName = "Test2";

// { BLOQUEDIRECCIONES \\c 1 \\d \\e Prueba2 \\f Prueba3 }
field.NameAndAddressFormat = "Test3";

// { BLOQUEDIRECCIÓN \\c 1 \\d \\e Prueba2 \\f Prueba3 \\l \"Prueba 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
