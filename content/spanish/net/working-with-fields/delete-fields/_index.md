---
title: Eliminar campos
linktitle: Eliminar campos
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para eliminar campos de combinación en sus documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/delete-fields/
---

Explicar cómo utilizar la función "Eliminar campos" en Aspose. En Words para .NET, hemos creado una guía paso a paso a continuación. 

Es importante seguir cada paso de cerca para lograr los resultados deseados. 

## Paso 1: crear un nuevo documento

En este fragmento de código comenzamos creando un nuevo documento vacío usando la siguiente línea: 

```csharp
Document doc = new Document();
```

## Paso 2: eliminar campos de combinación

 Para eliminar todos los campos de combinación presentes en el documento utilizamos el`DeleteFields()` función. 

Esto es particularmente útil si desea conservar sólo el contenido estático y eliminar cualquier información de combinación. 

### Ejemplo de código fuente para eliminar campos con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar documento existente.
Document doc = new Document(dataDir + "YourDocument.docx");

// Eliminar campos de combinación.
doc.MailMerge.DeleteFields();

// Guarde el documento modificado.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 En nuestro ejemplo, primero cargamos un documento existente antes de llamar`DeleteFields()`. Finalmente guardamos el documento modificado con un nuevo nombre de archivo. 

Para eliminar eficazmente los campos de combinación de un documento utilizando la función "Eliminar campos" de Aspose.Words para .NET, siga el ejemplo de este ejemplo. 

Recuerde siempre reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta de su directorio específico. 

Nuestra guía sobre cómo implementar la funcionalidad "Eliminar campos" a través de Aspose.Words para .NET ha concluido.

### Preguntas frecuentes

#### P: ¿Qué es un campo en Aspose.Words?

R: Un campo en Aspose.Words es una estructura de documento que representa texto generado automáticamente o un valor calculado. Los campos se utilizan para mostrar información dinámica en un documento, como números de página, fechas, campos de combinación de correspondencia, etc.

#### P: ¿Cómo eliminar un campo en un documento de Word con Aspose.Words?

R: Para eliminar un campo en un documento de Word con Aspose.Words, puede seguir estos pasos:

1. Importe la clase Documento desde el espacio de nombres Aspose.Words.
2. Cree una instancia de Documento cargando su documento existente.
3. Utilice el método RemoveFields para eliminar todos los campos del documento.

#### P: ¿Puedo eliminar campos específicos en lugar de eliminar todos los campos de un documento?

R: Sí, puede eliminar campos específicos en lugar de eliminar todos los campos de un documento. Para hacer esto, debe acceder a cada campo individualmente y utilizar el método Eliminar para eliminarlo.

#### P: ¿Cómo puedo comprobar si existe un campo en un documento de Word antes de eliminarlo?

R: Para verificar si un campo existe en un documento de Word antes de eliminarlo, puede usar el método Contiene de la colección Campos para encontrar el campo especificado. Este método devuelve un valor booleano que indica si el campo existe o no.

#### P: ¿Cuáles son los efectos de eliminar un campo en el resto del documento?

R: Cuando elimina un campo en un documento de Word, el campo se elimina del documento y el texto generado o el valor calculado asociado con el campo se elimina. Esto puede afectar el diseño del documento, ya que se eliminará el contenido generado por el campo.