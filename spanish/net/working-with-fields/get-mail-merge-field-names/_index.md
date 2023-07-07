---
title: Obtener nombres de campos de combinación de correspondencia
linktitle: Obtener nombres de campos de combinación de correspondencia
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a obtener nombres de campos de combinación de correspondencia en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/get-mail-merge-field-names/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Obtener nombres de campo de combinación" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargar el documento

El primer paso es cargar el documento donde desea obtener los nombres de los campos de combinación.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Asegúrese de reemplazar "SU ARCHIVO DE DOCUMENTO" con el nombre de su propio archivo.

## Paso 3: Obtener nombres de campos de combinación

 usamos el`GetFieldNames()` método para obtener una matriz que contiene los nombres de los campos de combinación presentes en el documento.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 El`fieldNames` La variable ahora contiene los nombres de los campos de combinación.

### Ejemplo de código fuente para obtener nombres de campo de combinación con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Obtener nombres de campos de combinación.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Muestra el número de campos de combinación.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 En este ejemplo, cargamos un documento, obtuvimos los nombres de los campos de combinación usando el`GetFieldNames()` y mostró el número de campos de combinación presentes en el documento.

Esto concluye nuestra guía sobre el uso de la función "Obtener nombres de campo de combinación" con Aspose.Words para .NET.

### preguntas frecuentes

#### P1: ¿Qué es la combinación de correspondencia en Aspose.Words?

La combinación de correspondencia en Aspose.Words es un proceso para combinar datos de una fuente externa (por ejemplo, una hoja de cálculo o una base de datos de Excel) con una plantilla de documento de Word para crear documentos personalizados. Esto facilita la generación automatizada de cartas, informes y otros documentos similares.

#### P2: ¿Cómo obtengo la lista de campos de combinación de correspondencia disponibles en un documento de Word?

Para obtener la lista de campos de combinación de correspondencia disponibles en un documento de Word, puede seguir estos pasos:

1. Importe las clases Document y MailMergeFieldNames del espacio de nombres Aspose.Words.
2. Cree una instancia de documento cargando su documento de Word.
3. Utilice el método GetMailMergeFieldNames del objeto Document para obtener la lista de campos de combinación de correspondencia disponibles.

Aquí hay un código de muestra para ilustrar el proceso:

```csharp
// Importar los espacios de nombres necesarios
using Aspose.Words;
using Aspose.Words.MailMerging;

// Cargar el documento existente
Document document = new Document("FilePath");

// Obtener una lista de campos de combinación de correspondencia
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Desplazarse por los campos de combinación de correspondencia disponibles
foreach (string fieldName in fieldNames)
{
     // Haz algo con el nombre del campo.
     Console.WriteLine(fieldName);
}
```
### Preguntas frecuentes

#### P: ¿Qué es la combinación de correspondencia en Aspose.Words?

R: La combinación de correspondencia en Aspose.Words es un proceso para combinar datos de una fuente externa (por ejemplo, una hoja de cálculo o una base de datos de Excel) con una plantilla de documento de Word para crear documentos personalizados. Esto facilita la generación automatizada de cartas, informes y otros documentos similares.

#### P: ¿Cómo obtengo la lista de campos de combinación de correspondencia disponibles en un documento de Word?

R: Para obtener la lista de campos de combinación de correspondencia disponibles en un documento de Word, puede seguir estos pasos:

1. Importe las clases Document y MailMergeFieldNames del espacio de nombres Aspose.Words.
2. Cree una instancia de documento cargando su documento de Word.
3. Utilice el método GetMailMergeFieldNames del objeto Document para obtener la lista de campos de combinación de correspondencia disponibles.

#### P: ¿Puedo obtener campos de combinación de correspondencia de una fuente de datos externa, como una hoja de cálculo de Excel?

R: Sí, puede obtener los campos de combinación de correspondencia de una fuente de datos externa, como una hoja de cálculo de Excel. Para ello, puede utilizar las funciones de enlace de datos de Aspose.Words para establecer una conexión con la fuente de datos y obtener los nombres de los campos disponibles.

#### P: ¿Es posible filtrar los campos de combinación de correspondencia según ciertos criterios?

R: Sí, es posible filtrar los campos de combinación de correspondencia según ciertos criterios. Puede usar expresiones regulares o condiciones específicas para filtrar campos de combinación de correspondencia y obtener solo aquellos que cumplan con sus criterios específicos.

#### P: ¿Cómo puedo manipular los campos de combinación de correspondencia en Aspose.Words?

R: Para manipular los campos de combinación de correspondencia en Aspose.Words, puede usar los métodos y propiedades proporcionados por los objetos Document y MailMergeField. Puede agregar, eliminar o actualizar campos de combinación de correspondencia, así como recuperar y editar valores asociados con campos.