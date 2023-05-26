---
title: Regiones editables sin restricciones
linktitle: Regiones editables sin restricciones
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear áreas editables sin restricciones en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/unrestricted-editable-regions/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de áreas editables sin restricciones de Aspose.Words para .NET. Esta función le permite definir áreas en un documento de Word donde el contenido se puede editar sin restricciones, incluso si el resto del documento es de solo lectura. Siga los pasos a continuación:

## Paso 1: Cargar el documento y configurar la protección

Comience cargando el documento existente:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Proteja el documento configurando el tipo de protección de solo lectura y la contraseña

## Paso 2: Crear un área editable

Comience creando un área editable usando los objetos EditableRangeStart y EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Se crea un objeto EditableRange para el EditableRangeStart que acabamos de crear.
EditableRange editableRange = edRangeStart.EditableRange;

// Ponga algo dentro del rango editable.
builder.Writeln("Paragraph inside first editable range");

// Un rango editable está bien formado si tiene un inicio y un final.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Paso 3: agregue contenido fuera de las áreas editables

Puede agregar contenido fuera de las áreas editables, que seguirán siendo de solo lectura:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Paso 4: Guarde el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento con áreas editables.

### Ejemplo de código fuente para regiones editables sin restricciones usando Aspose.Words para .NET

Aquí está el código fuente completo para áreas editables sin restricciones usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue un documento y hágalo como de solo lectura.
	Document doc = new Document(MyDir + "Document.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	doc.Protect(ProtectionType.ReadOnly, "MyPassword");

	builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

	// Inicie un rango editable.
	EditableRangeStart edRangeStart = builder.StartEditableRange();
	// Se crea un objeto EditableRange para el EditableRangeStart que acabamos de crear.
	EditableRange editableRange = edRangeStart.EditableRange;

	// Ponga algo dentro del rango editable.
	builder.Writeln("Paragraph inside first editable range");

	// Un rango editable está bien formado si tiene un inicio y un final.
	EditableRangeEnd edRangeEnd = builder.EndEditableRange();

	builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

	doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Siguiendo estos pasos, puede crear fácilmente áreas editables sin restricciones en su documento de Word con Aspose.Words para .NET.


