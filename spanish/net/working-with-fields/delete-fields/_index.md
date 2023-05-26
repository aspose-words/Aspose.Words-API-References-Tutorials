---
title: Eliminar campos
linktitle: Eliminar campos
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para eliminar campos de combinación en sus documentos de Word utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/delete-fields/
---

Para explicar cómo usar la función "Eliminar campos" en Aspose. Words para .NET hemos creado una guía paso a paso a continuación. 

Es importante seguir cada paso de cerca para lograr los resultados deseados. 

## Paso 1: Creación de un nuevo documento

En este fragmento de código, comenzamos creando un nuevo documento vacío usando la siguiente línea: 

```csharp
Document doc = new Document();
```

## Paso 2: eliminar campos de combinación

 Para eliminar todos los campos de combinación presentes en el documento, usamos el`DeleteFields()` función. 

Esto es particularmente útil si desea mantener solo el contenido estático y eliminar cualquier información de combinación. 

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

Para eliminar de forma eficaz los campos de combinación de un documento mediante la función "Eliminar campos" de Aspose.Words para .NET, siga este ejemplo. 

Recuerde siempre reemplazar "SU DIRECTORIO DE DOCUMENTOS" con su ruta de directorio específica. 

Nuestra guía sobre la implementación de la funcionalidad "Eliminar campos" a través de Aspose.Words para .NET ha concluido.