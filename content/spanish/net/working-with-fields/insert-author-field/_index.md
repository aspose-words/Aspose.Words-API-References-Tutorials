---
title: Insertar campo de autor
linktitle: Insertar campo de autor
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar un campo AUTOR en sus documentos de Word con Aspose.Words para .NET. Especifique el nombre del autor para personalizar sus documentos.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-author-field/
---


Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Insertar un campo AUTOR" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código proporcionado, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear el documento y el párrafo

Comenzamos creando un nuevo documento y buscando el primer párrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Paso 3: Insertar el campo AUTOR

 Usamos el`AppendField()` Método para insertar un campo AUTOR en el párrafo.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Luego configuramos el campo`AuthorName` propiedad para especificar el nombre del autor.

```csharp
field. AuthorName = "Test1";
```

 Finalmente llamamos al`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo del código fuente para insertar un campo AUTOR con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserte el campo AUTOR.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo AUTOR, configuramos el nombre del autor y guardamos el documento con un nombre de archivo específico.

Con esto concluye nuestra guía sobre el uso de la función "Insertar campo AUTOR" con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Qué es un campo de autor en Aspose.Words?

R: Un campo de autor en Aspose.Words es un campo especial que inserta y actualiza automáticamente el nombre del autor en un documento de Word. A menudo se utiliza para indicar quién creó o modificó el documento.

#### P: ¿Cómo actualizar el campo de autor en un documento de Word con Aspose.Words?

R: El campo de autor en un documento de Word se puede actualizar para reflejar el nombre del autor actual. Para ello, puede utilizar el método UpdateFields disponible en la clase Documento. Este método actualizará todos los campos del documento, incluido el campo de autor.

#### P: ¿Es posible personalizar el formato del campo de autor en un documento de Word?

R: Sí, es posible personalizar el formato del campo de autor en un documento de Word. De forma predeterminada, el campo de autor simplemente muestra el nombre del autor. Sin embargo, puede agregar información adicional, como la fecha y hora de la modificación, utilizando las opciones de formato disponibles en Aspose.Words.

#### P: ¿El campo de autor es sensible a cambios posteriores en el nombre del autor?

R: Sí, el campo de autor es sensible a cambios posteriores en el nombre del autor. Si cambia el nombre del autor en las propiedades del documento, el campo de autor se actualizará automáticamente con el nuevo nombre al actualizar los campos del documento.