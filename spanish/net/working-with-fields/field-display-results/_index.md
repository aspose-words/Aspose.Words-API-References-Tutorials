---
title: Resultados de visualización de campo
linktitle: Resultados de visualización de campo
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para mostrar resultados de campo en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/field-display-results/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Mostrar resultados de campo" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargar el documento

El primer paso es cargar el documento en el que desea mostrar los resultados del campo.

```csharp
Document document = new Document(dataDir + "Miscellaneous fields.docx");
```

Asegúrese de reemplazar "Miscellaneous Fields.docx" con el nombre de su propio archivo.

## Paso 3: Actualizar campos

 usamos el`UpdateFields()` para actualizar todos los campos del documento.

```csharp
document. UpdateFields();
```

Este paso es importante porque garantiza que los resultados de los campos se muestren correctamente.

## Paso 4: Visualización de resultados de campo

 usamos un`foreach` bucle para recorrer todos los campos del documento y mostrar sus resultados.

```csharp
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

 En cada iteración del ciclo, accedemos a la`DisplayResult` propiedad del campo para obtener el resultado mostrado.

### Ejemplo de código fuente para mostrar resultados de campo con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento.
Document document = new Document(dataDir + "Miscellaneous fields.docx");

// Actualizar campos.
document. UpdateFields();

// Visualización de resultados de campo.
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

En este ejemplo, cargamos un documento, actualizamos todos los campos y luego recorrimos los campos para mostrar sus resultados. Puede personalizar este paso utilizando su propia lógica para procesar los resultados de los campos.

Esto concluye nuestra guía para usar la función "Mostrar resultados de campo" con Aspose.Words para .NET.