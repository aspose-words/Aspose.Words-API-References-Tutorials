---
title: Sección no restringida
linktitle: Sección no restringida
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a definir secciones sin restricciones en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/unrestricted-section/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de sección sin restricciones de Aspose.Words para .NET. Esta característica le permite definir secciones específicas en un documento de Word que no están protegidas, incluso si el resto del documento está protegido. Siga los pasos a continuación:

## Paso 1: Crear el Documento y las Secciones

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Agregar contenido al documento
Use el objeto DocumentBuilder para agregar contenido al documento e insertar saltos de sección:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Paso 3: proteger el documento y las secciones

La protección de secciones solo funciona cuando la protección de documentos está habilitada y solo se permite la edición en campos de formulario. Puede proteger el documento usando el método Protect() del objeto Documento:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Asegúrese de especificar el tipo correcto de protección y establecer la contraseña deseada.

## Paso 4: Deshabilitar la protección para una sección específica

De manera predeterminada, todas las secciones están protegidas, pero puede deshabilitar selectivamente la protección para una sección específica utilizando la propiedad ProtectedForForms del objeto Sección:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

En este ejemplo, la protección está deshabilitada para la primera sección.

## Paso 5: Guarde el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento con secciones sin restricciones.

### Ejemplo de código fuente para la sección sin restricciones usando Aspose.Words para .NET

Aquí está el código fuente completo para la sección sin restricciones usando Aspose.Words para .NET:


```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inserta dos secciones con algo de texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// La protección de secciones solo funciona cuando la protección de documentos está activada y solo se permite la edición en campos de formulario.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// De forma predeterminada, todas las secciones están protegidas, pero podemos desactivar la protección de forma selectiva.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Siguiendo estos pasos, podrá definir fácilmente secciones sin restricciones en su documento de Word con Aspose.Words para .NET.

