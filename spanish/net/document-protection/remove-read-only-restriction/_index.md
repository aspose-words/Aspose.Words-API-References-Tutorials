---
title: Eliminar restricción de solo lectura
linktitle: Eliminar restricción de solo lectura
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a eliminar la restricción de solo lectura de un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/remove-read-only-restriction/
---
En este tutorial, lo guiaremos a través de los pasos para usar Aspose.Words para la función de eliminación de restricciones de solo lectura de .NET. Esta función le permite eliminar la restricción de solo lectura de un documento de Word para que sea editable. Siga los pasos a continuación:

## Paso 1: Creación del documento y configuración de la protección

Comience creando una instancia de la clase Documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Establezca una contraseña para el documento utilizando la propiedad SetPassword() del objeto WriteProtection:

Asegúrese de reemplazar "MyPassword" con la contraseña real que utilizó para proteger el documento.

## Paso 2: eliminar la restricción de solo lectura

Para eliminar la restricción de solo lectura, establezca la propiedad ReadOnlyRecommended en falso:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Paso 3: aplique la protección sin restricciones

Finalmente, aplique protección sin restricciones utilizando el método Protect() del objeto Documento:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento sin la restricción de solo lectura.

### Ejemplo de código fuente para eliminar la restricción de solo lectura con Aspose.Words para .NET

Aquí está el código fuente completo para eliminar la restricción de solo lectura usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// Introduzca una contraseña de hasta 15 caracteres.
	doc.WriteProtection.SetPassword("MyPassword");

	// Elimina la opción de solo lectura.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Aplicar protección contra escritura sin ninguna protección.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

Siguiendo estos pasos, puede eliminar fácilmente la restricción de solo lectura de un documento de Word con Aspose.Words para .NET.

