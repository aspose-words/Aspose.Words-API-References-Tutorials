---
title: Protección de solo lectura
linktitle: Protección de solo lectura
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a proteger sus documentos de Word de solo lectura con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/read-only-protection/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función de protección de solo lectura de Aspose.Words para .NET. Esta función le permite hacer que un documento de Word sea de solo lectura para evitar modificaciones no autorizadas. Siga los pasos a continuación:

## Paso 1: Creación del documento y aplicación de la protección

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: escribir contenido en el documento
Utilice el objeto DocumentBuilder para escribir contenido en el documento:

```csharp
builder.Write("Open document as read-only");
```

## Paso 3: establezca la contraseña y haga que el documento sea de solo lectura

Establezca una contraseña para el documento utilizando la propiedad SetPassword() del objeto WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Asegúrese de reemplazar "MyPassword" con la contraseña real que desea usar.

## Paso 4: Aplicar documento de solo lectura

Haga que el documento sea de solo lectura configurando la propiedad ReadOnlyRecommended en verdadero:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Paso 5: aplique la protección de solo lectura y guarde el documento

Finalmente, aplique la protección de solo lectura utilizando el método Protect() del objeto Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento protegido.

### Ejemplo de código fuente para la protección de solo lectura con Aspose.Words para .NET

Aquí está el código fuente completo para la protección de solo lectura usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// Introduzca una contraseña de hasta 15 caracteres.
	doc.WriteProtection.SetPassword("MyPassword");

	// Haga que el documento sea de solo lectura.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Aplique la protección contra escritura como de solo lectura.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Siguiendo estos pasos, puede proteger fácilmente sus documentos

