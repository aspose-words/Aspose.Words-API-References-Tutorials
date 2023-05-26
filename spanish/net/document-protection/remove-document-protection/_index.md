---
title: Eliminar protección de documentos
linktitle: Eliminar protección de documentos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a eliminar la protección de un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/remove-document-protection/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de desprotección de documentos de Aspose.Words para .NET. Esta característica le permite eliminar la protección de un documento de Word para que sea accesible para su posterior edición. Siga los pasos a continuación:

## Paso 1: crear el documento y agregar contenido

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Agregar contenido al documento

Use el objeto DocumentBuilder para agregar contenido al documento:

```csharp
builder.Writeln("Text added to a document.");
```

## Paso 3: Desproteger Documento

Para desproteger el documento, puede utilizar el método Unprotect() del objeto Documento. Puede optar por eliminar la protección sin contraseña o con la contraseña correcta. Eliminación de la protección sin contraseña:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Asegúrese de reemplazar "nueva contraseña" con la contraseña correcta del documento.

## Paso 4: Guarda el documento sin protección

Finalmente, guarde el documento sin protección usando el método Save() del objeto Documento:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento sin protección.

### Ejemplo de código fuente para eliminar la protección de documentos con Aspose.Words para .NET

Aquí está el código fuente completo para desproteger el documento usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	// Se puede quitar la protección de los documentos sin contraseña o con la contraseña correcta.
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Siguiendo estos pasos, puede eliminar fácilmente la protección del documento de Word con Aspose.Words para .NET.
