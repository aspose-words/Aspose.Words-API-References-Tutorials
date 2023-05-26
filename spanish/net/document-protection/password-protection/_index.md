---
title: Protección de contraseña
linktitle: Protección de contraseña
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a proteger con contraseña sus documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/password-protection/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de protección con contraseña de Aspose.Words para .NET. Esta función le permite proteger un documento de Word con una contraseña para garantizar su confidencialidad. Siga los pasos a continuación:

## Paso 1: Creación del documento y aplicación de la protección

Comience creando una instancia de la clase Documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Paso 2: Aplicar protección con contraseña

Luego puede aplicar la protección con contraseña utilizando el método Protect() del objeto Documento:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Asegúrese de reemplazar "contraseña" con la contraseña real que desea usar para proteger el documento.

## Paso 3: Guardar el Documento Protegido

Finalmente, puede guardar el documento protegido usando el método Save() del objeto Documento:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento protegido.

### Ejemplo de código fuente para Protección con contraseña usando Aspose.Words para .NET

Aquí está el código fuente completo para la protección con contraseña usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//Aplicar protección de documentos.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

Recuerde reemplazar "SU DIRECTORIO DE DOCUMENTOS" con el directorio de sus documentos y "contraseña" con la contraseña real que desea utilizar.

