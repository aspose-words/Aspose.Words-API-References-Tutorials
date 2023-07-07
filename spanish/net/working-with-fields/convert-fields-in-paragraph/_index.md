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

### Preguntas frecuentes

#### P: ¿Qué es un campo de conversión en Aspose.Words?

R: Un campo de conversión en Aspose.Words es un tipo de campo que convierte un valor o una expresión en otro formato o tipo de datos. Por ejemplo, puede usar un campo de conversión para convertir una fecha a un formato específico, un número a texto o realizar otros tipos de conversiones.

#### P: ¿Cómo insertar un campo de conversión en un párrafo con Aspose.Words?

R: Para insertar un campo de conversión en un párrafo con Aspose.Words, puede seguir estos pasos:

1. Importe la clase Document del espacio de nombres Aspose.Words.
2. Cree una instancia de Documento cargando su documento existente.
3. Obtenga el párrafo donde desea insertar el campo de conversión.
4. Utilice el método InsertField para insertar el campo de conversión con la sintaxis correcta.

#### P: ¿Qué formatos de conversión admite Aspose.Words?

R: Aspose.Words admite una amplia gama de formatos de conversión en campos, incluidos formatos de fecha, formatos de número, formatos de texto, formatos de moneda, formatos de porcentaje y más. Puede consultar la documentación de Aspose.Words para obtener una lista completa de los formatos de conversión disponibles.

#### P: ¿Cómo actualizar un campo de conversión en un documento de Word con Aspose.Words?

R: Para actualizar un campo de conversión en un documento de Word con Aspose.Words, puede usar el método UpdateFields. Este método recorre el documento y actualiza todos los campos, incluidos los campos de conversión, y vuelve a calcular los valores en función de los datos actuales.