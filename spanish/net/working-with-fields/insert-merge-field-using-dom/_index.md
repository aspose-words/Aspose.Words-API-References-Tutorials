---
title: Insertar campo de combinación usando DOM
linktitle: Insertar campo de combinación usando DOM
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar campos de combinación de campos personalizados en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-merge-field-using-dom/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que utiliza la función "Insertar campo de combinación de campo" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

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

 usamos el`MoveTo()` del DocumentBuilder para mover el cursor al párrafo donde queremos insertar el campo de combinación de campos.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Paso 4: Inserción del campo de combinación de campos

 Usamos el DocumentBuilder`InsertField()` para insertar un campo de combinación de campos en el párrafo.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

continuación, configuramos las propiedades del campo de combinación de campos especificando las opciones adecuadas, como el nombre del campo, el texto antes y después del campo y las opciones de formato vertical.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo de código fuente para insertar un campo de combinación de campos con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mover el cursor al párrafo.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Insertar campo de combinación de campos.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Actualice el campo.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

En este ejemplo, creamos un nuevo documento, movimos el cursor al párrafo deseado y luego insertamos un campo de combinación de campos en el documento.

### Preguntas frecuentes

#### P: ¿Cómo puedo insertar un campo de combinación en un documento de Word usando Aspose.Words para .NET con el DOM?

R: Para insertar un campo de combinación en un documento de Word usando Aspose.Words para .NET con DOM, puede seguir estos pasos:

1. Navegue hasta el párrafo donde desea insertar el campo de combinación.
2.  Crear un`FieldMergeField` objeto.
3. Establezca las propiedades del campo de combinación, como el nombre del campo y las opciones de formato.
4.  Agregue el campo de combinación al párrafo usando el`Paragraph.AppendChild` método.

#### P: ¿Cómo puedo especificar los datos de origen para el campo de combinación en Aspose.Words para .NET?

R: Para especificar los datos de origen para el campo de combinación en Aspose.Words para .NET, puede usar el`FieldMergeField.FieldName` para establecer el nombre del campo de combinación, que es el nombre de un campo en una fuente de datos externa, como un archivo CSV, una base de datos, etc. También puede usar el`FieldMergeField.Text` método para establecer el valor del campo de combinación directamente.

#### P: ¿Puedo personalizar la apariencia del campo de combinación en un documento de Word con Aspose.Words para .NET?

 R: Sí, puede personalizar la apariencia del campo de combinación en un documento de Word con Aspose.Words para .NET. Puede configurar las opciones de formato como mayúsculas y minúsculas, fuente, color, etc. usando las propiedades del`FieldMergeField` objeto.

#### P: ¿Cómo puedo verificar si un campo de combinación se insertó correctamente en un documento de Word con Aspose.Words para .NET?

 R: Para verificar si un campo de combinación se insertó correctamente, puede explorar el contenido del documento y buscar instancias de campos de combinación. Puede utilizar los métodos y propiedades de la`Document` objeto para acceder a párrafos, campos y otros elementos del documento.

#### P: ¿Insertar un campo de combinación usando DOM afecta la estructura del documento de Word con Aspose.Words para .NET?

R: Insertar un campo de combinación usando el DOM no afecta directamente la estructura del documento de Word. Sin embargo, agrega un nuevo elemento de campo al contenido del documento. Puede manipular la estructura del documento agregando, eliminando o modificando los elementos existentes según sus necesidades.