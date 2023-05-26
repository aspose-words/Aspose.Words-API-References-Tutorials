---
title: Convertir campos en documento
linktitle: Convertir campos en documento
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para convertir campos de documentos a texto usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/convert-fields-in-document/
---

En este tutorial, lo guiaremos paso a paso utilizando la función ConvertFieldsInDocument del software Aspose.Words para .NET. Explicaremos en detalle el código fuente de C# necesario para esta función y proporcionaremos formatos de salida de descuento de muestra.

## Paso 1: Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Aspose.Words para .NET instalado en su máquina de desarrollo.
- Un documento de Word que contiene campos vinculados que desea convertir en texto.
- Un directorio de documentos donde puede guardar el documento transformado.

## Paso 2: Configuración del entorno
Asegúrese de haber configurado correctamente su entorno de desarrollo para usar Aspose.Words para .NET. Importe los espacios de nombres necesarios y establezca la ruta a su directorio de documentos.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 3: Cargue el documento
 Utilizar el`Document` clase de Aspose.Words para cargar el documento de Word que contiene los campos vinculados que desea convertir.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## Paso 4: Convierta los campos enlazados en texto
 Utilizar el`Unlink()` método para convertir todos los campos de tipo "IF" encontrados en el documento a texto. Este método se utiliza para transformar campos vinculados en su contenido textual.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## Paso 5: Guarde el documento transformado
 Utilizar el`Save()` para guardar el documento con los campos convertidos a texto en el directorio de documentos especificado.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Ejemplo de código fuente para ConvertFieldsInDocument usando Aspose.Words para .NET

Aquí está el código fuente completo para la función ConvertFieldsInDocument:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// Pase los parámetros apropiados para convertir todos los campos IF que se encuentran en el documento (incluidos los encabezados y pies de página) en texto.
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// Guarde el documento con los campos transformados en disco.
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Conclusión
La función ConvertFieldsInDocument de Aspose.Words para .NET es una poderosa herramienta para convertir campos vinculados en un documento de Word a texto. 