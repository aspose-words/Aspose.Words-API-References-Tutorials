---
title: Insertar campo incluye texto sin generador de documentos
linktitle: Insertar campoIncludeText sin generador de documentos
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo insertar un campo FieldIncludeText en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la funcionalidad "Insertar un campo FieldIncludeText" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

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

## Paso 3: Insertar el campo FieldIncludeText

 Usamos el`AppendField()` método para insertar un campo FieldIncludeText en el párrafo.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Luego configuramos las propiedades del campo FieldIncludeText especificando el nombre del marcador y el nombre del archivo fuente.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

A continuación, agregamos el párrafo al cuerpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Finalmente llamamos al`Update()` método para actualizar el campo.

```csharp
fieldIncludeText.Update();
```

### Ejemplo del código fuente para insertar un campo FieldIncludeText con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea el documento y el párrafo.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Insertar campo FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, inicializamos un párrafo, insertamos un FieldIncludeTexten especificando el nombre del marcador y el nombre del archivo fuente, y guardamos el documento con un nombre de archivo específico.

Con esto concluye nuestra guía sobre el uso de la función "Insertar un FieldIncludeText" con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo puedo especificar el archivo fuente para el campo de inclusión de texto en Aspose.Words para .NET?

 R: Para especificar el archivo fuente para el campo de inclusión de texto en Aspose.Words para .NET, puede usar el`FieldIncludeText.SourceFullName`propiedad para establecer la ruta completa del archivo fuente. Asegúrese de que el archivo fuente sea accesible y contenga el contenido que desea incluir en el campo de inclusión de texto.

#### P: ¿Puedo incluir texto de una macro en el campo de inclusión de texto con Aspose.Words para .NET?

 R: Sí, puede incluir texto de una macro en el campo de inclusión de texto con Aspose.Words para .NET. Puedes usar el`FieldIncludeText.IncludeText` propiedad para especificar el nombre de la macro cuyo contenido debe incluirse en el campo.

#### P: ¿La inserción de un campo de inclusión de texto sin el generador de documentos afecta la estructura del documento de Word con Aspose.Words para .NET?

R: Insertar un campo de inclusión de texto sin el generador de documentos no afecta directamente la estructura del documento de Word. Sin embargo, agrega un nuevo elemento de campo al contenido del documento. Puede manipular la estructura del documento agregando, eliminando o modificando los elementos existentes según sus necesidades.

#### P: ¿Puedo personalizar la apariencia del campo de inclusión de texto en un documento de Word con Aspose.Words para .NET?

R: La inclusión del campo de texto no personaliza directamente su apariencia en un documento de Word. Sin embargo, puede formatear el texto incluido usando las propiedades de párrafo, propiedades de fuente y otros objetos de formato disponibles en Aspose.Words para .NET.