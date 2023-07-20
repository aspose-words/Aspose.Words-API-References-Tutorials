---
title: Insertar ASKField sin Document Builder
linktitle: Insertar ASKField sin Document Builder
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un campo ASK en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la función "Insertar un campo ASK sin DocumentBuilder" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

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

## Paso 3: Inserción del campo ASK

 usamos el`AppendField()` para insertar un campo ASK en el párrafo.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Luego configuramos las diversas propiedades del campo ASK especificando los valores deseados.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo del código fuente para insertar un campo ASK sin DocumentBuilder con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserte el campo ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo ASK sin usar DocumentBuilder, configuramos las diversas propiedades del campo y guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre el uso de la función "Insertar campo ASK sin DocumentBuilder" con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Qué es un campo ASK en Aspose.Words?

R: Un campo ASK en Aspose.Words se usa para hacerle una pregunta al usuario al abrir un documento. A menudo se usa para solicitar información o comentarios específicos que pueden variar de un usuario a otro.

#### P: ¿Cómo insertar el campo ASK en un documento de Word sin utilizar Document Builder en Aspose.Words?

R: Para insertar un campo ASK en un documento de Word sin utilizar Document Builder en Aspose.Words, puede seguir estos pasos:

1. Importe la clase Documento y Campo desde el espacio de nombres Aspose.Words.Fields.
2. Cree una instancia de Documento cargando su documento existente.
3. Utilice el método InsertField para insertar un campo ASK especificando el nombre de la pregunta.
4. Guarde el documento.

#### P: ¿Cómo obtengo la respuesta del usuario para un campo ASK en un documento de Word?

R: Para obtener la respuesta del usuario para un campo ASK en un documento de Word, puede usar el método GetFieldNames disponible en la clase Documento. Este método devuelve una lista de los nombres de los campos presentes en el documento. A continuación, puede comprobar si el nombre del campo ASK está presente en la lista y recuperar la respuesta asociada.

#### P: ¿Se puede usar el campo ASK para solicitar más información al usuario?

R: Sí, el campo ASK se puede usar para solicitar múltiples datos del usuario. Puede insertar múltiples campos ASK en su documento, cada uno con una pregunta diferente. Cuando se abre el documento, se le solicitará al usuario las respuestas correspondientes.