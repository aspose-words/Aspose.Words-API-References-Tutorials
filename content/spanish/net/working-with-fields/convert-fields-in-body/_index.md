---
title: Convertir campos en cuerpo
linktitle: Convertir campos en cuerpo
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar Aspose.Words para .NET para convertir campos de página en texto en el cuerpo de un documento de Word.
type: docs
weight: 10
url: /es/net/working-with-fields/convert-fields-in-body/
---

En este tutorial paso a paso, le explicaremos cómo utilizar la función ConvertFieldsInBody de Aspose.Words para .NET utilizando el código fuente C# proporcionado. Esta función le permite convertir campos específicos en el cuerpo de su documento a texto sin formato, lo que facilita el procesamiento de sus documentos. Siga los pasos a continuación para utilizar esta función de manera efectiva.

## Paso 1: requisitos previos

Antes de comenzar, asegúrese de haber instalado Aspose.Words para .NET y de tener un documento listo para procesar. También asegúrese de tener la ruta del directorio a sus documentos.

## Paso 2: Cargue el documento

Comience declarando una variable para la ruta a su directorio de documentos, luego use esa variable para inicializar un objeto Documento desde el documento especificado. En nuestro ejemplo, el documento se llama "Campos vinculados.docx".

```csharp
// La ruta a su directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Paso 3: convertir campos de página a texto sin formato

 Ahora que el documento está cargado, podemos pasar a los pasos de conversión. Para convertir los campos de la página a texto sin formato en el cuerpo de la primera sección, puede utilizar el`Range.Fields` método para obtener todos los campos en el rango especificado y luego filtrar los campos de tipo`FieldType.FieldPage` . Entonces puedes usar el`ForEach` método para recorrer cada campo y llamar al`Unlink()` método para convertirlo a texto sin formato.

```csharp
// Pase los parámetros apropiados para convertir los campos de la página a texto sin formato en el cuerpo de la primera sección.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Paso 4: guarde el documento modificado

Una vez que haya convertido los campos de la página a texto sin formato, puede guardar el documento modificado usando el`Save()` método y especificando la ruta y el nombre del archivo de salida. En nuestro ejemplo, lo guardamos como "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Código fuente de ejemplo para convertir campos en el cuerpo con Aspose.Words para .NET

Aquí está el ejemplo de código fuente completo para convertir campos en el cuerpo usando Aspose.Words para .NET:

```csharp
// La ruta a su directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Linked fields.docx");

// Pase los parámetros apropiados para convertir los campos de la página a texto sin formato en el cuerpo de la primera sección.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Preguntas frecuentes

#### P: ¿Aspose.Words es compatible con diferentes versiones de Microsoft Word?

R: Sí, Aspose.Words es compatible con varias versiones de Microsoft Word, incluidas Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 y Word 2019.

#### P: ¿Puede Aspose.Words manejar estructuras de campos complejas?

R: ¡Absolutamente! Aspose.Words proporciona un amplio soporte para estructuras de campos complejas, incluidos campos anidados, cálculos y expresiones condicionales. Puede aprovechar la potente API para trabajar con cualquier tipo de estructura de campo.

#### P: ¿Aspose.Words admite operaciones de actualización de campos?

R: Sí, Aspose.Words le permite actualizar campos mediante programación. Puede actualizar fácilmente los valores de los campos, actualizar los cálculos y realizar otras operaciones relacionadas con los campos mediante la API.

#### P: ¿Puedo convertir campos a texto sin formato usando Aspose.Words?

R: ¡Ciertamente! Aspose.Words proporciona métodos para convertir campos a texto sin formato. Esto puede resultar útil cuando necesita extraer el contenido sin ningún formato o funcionalidad relacionada con el campo.

#### P: ¿Es posible generar documentos de Word con campos dinámicos usando Aspose.Words?

R: ¡Absolutamente! Aspose.Words ofrece funciones sólidas para generar documentos de Word con campos dinámicos. Puede crear plantillas con campos predefinidos y completarlas con datos dinámicamente, proporcionando una solución de generación de documentos flexible y eficiente.