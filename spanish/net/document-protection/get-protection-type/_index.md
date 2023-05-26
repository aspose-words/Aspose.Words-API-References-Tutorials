---
title: Obtener tipo de protección
linktitle: Obtener tipo de protección
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar la función Obtener tipo de protección de Aspose.Words para .NET para determinar el tipo de protección de un documento.
type: docs
weight: 10
url: /es/net/document-protection/get-protection-type/
---

Bienvenido a esta guía paso a paso que explica el código fuente de C# para la función Obtener tipo de protección de Aspose.Words para .NET. En este artículo, le mostraremos cómo utilizar esta potente función para determinar el tipo de protección de un documento. La protección de documentos es esencial para garantizar la confidencialidad e integridad de sus archivos. Lo guiaremos a través de los pasos necesarios para integrar Aspose.Words para .NET y usar la función Obtener tipo de protección.

## Paso 1: Cargar el documento

El primer paso para usar la función Obtener tipo de protección es cargar el documento en el que desea trabajar. Puede hacerlo utilizando la clase Document proporcionada por Aspose.Words para .NET. Aquí hay un código de muestra para cargar un documento desde un archivo:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Asegúrese de especificar la ruta correcta a su archivo de documento.

## Paso 2: Recuperación del tipo de protección

Después de cargar el documento, puede usar la propiedad ProtectionType del objeto Document para recuperar el tipo de protección aplicada al documento. Así es como puedes hacerlo:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Código fuente de ejemplo para Obtener tipo de protección usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Obtener tipo de protección usando Aspose.Words para .NET:

```csharp

	Document doc = new Document(MyDir + "Document.docx");
	ProtectionType protectionType = doc.ProtectionType;

```

## Conclusión

En este artículo, explicamos cómo usar la función Obtener tipo de protección de Aspose.Words para .NET para determinar el tipo de protección de un documento. Siguiendo los pasos descritos, podrá integrar fácilmente esta funcionalidad en sus propios proyectos de C# y manipular de manera eficiente los documentos protegidos. Aspose.Words para .NET ofrece una gran flexibilidad

