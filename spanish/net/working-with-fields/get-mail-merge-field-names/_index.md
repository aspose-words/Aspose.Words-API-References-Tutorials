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

### Ejemplo de código fuente para obtener nombres de campos de combinación con Aspose.Words para .NET

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