---
title: Insertar campo TOA sin generador de documentos
linktitle: Insertar campo TOA sin generador de documentos
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para insertar el campo TOA sin Document Builder usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-toafield-without-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Inserción de campo TOA" de Aspose.Words para .NET. Siga cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código proporcionado, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear el documento y el párrafo

Comenzamos creando un nuevo documento e inicializando un párrafo.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Paso 3: Insertar el campo TA

Usamos la clase FieldTA para insertar un campo TA en el párrafo.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Paso 4: Agregar el párrafo al cuerpo del documento

Agregamos el párrafo que contiene el campo TA al cuerpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Paso 5: Crear el párrafo para el campo TOA

Creamos un nuevo párrafo para el campo TOA.

```csharp
para = new Paragraph(doc);
```

## Paso 6: Insertar el campo TOA

Usamos la clase FieldToa para insertar un campo TOA en el párrafo.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Paso 7: Agregar el párrafo al cuerpo del documento

Agregamos el párrafo que contiene el campo TOA al cuerpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Paso 8: actualice el campo TOA

 Finalmente llamamos al`Update()` método para actualizar el campo TOA.

```csharp
fieldToa.Update();
```

### Ejemplo de código fuente para inserción de campos TOA sin Document Builder con Aspose.Words para .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Queremos insertar campos TA y TOA como este:
// { TA \c 1 \l "Valor 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Preguntas frecuentes

#### P: ¿Cómo personalizar la apariencia del campo TOA insertado en el documento de Word con Aspose.Words para .NET?

R: Puede personalizar la apariencia del campo TOA insertado utilizando las propiedades del`FieldTOA` objeto para especificar opciones de formato.

#### P: ¿Puedo agregar varios campos TOA en un solo documento de Word usando Aspose.Words para .NET?

R: Sí, puede agregar varios campos TOA en un solo documento de Word usando Aspose.Words para .NET. Simplemente repita los pasos de inserción para cada campo.

#### P: ¿Cómo puedo comprobar si un campo TOA se insertó correctamente en un documento de Word con Aspose.Words para .NET?

R: Para comprobar si un campo TOA se insertó correctamente, puede explorar el contenido del documento y buscar instancias de campo TOA.

#### P: ¿La inserción de un campo TOA sin utilizar DocumentBuilder afecta el formato de documentos de Word con Aspose.Words para .NET?

R: Insertar un campo TOA sin usar DocumentBuilder no afecta directamente el formato del documento de Word. Sin embargo, las opciones de formato del campo TOA pueden afectar el formato general del documento.