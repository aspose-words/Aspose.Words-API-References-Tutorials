---
title: Eliminar información personal
linktitle: Eliminar información personal
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para eliminar información personal de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/remove-personal-information/
---

En este tutorial, lo guiaremos a través del código fuente de C# para eliminar información personal de un documento con Aspose.Words para .NET. Esta función le permite eliminar información personal confidencial de un documento, como los datos de identificación del autor.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso, subiremos el documento de Word del que queremos eliminar la información personal. Use el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: Eliminar información personal

 Ahora habilitaremos la eliminación de información personal configurando el`RemovePersonalInformation` propiedad a`true`. Usa el siguiente código:

```csharp
doc.RemovePersonalInformation = true;
```

Este código activa la eliminación de información personal en el documento.

## Paso 4: Guardar el documento

Finalmente, guardaremos el documento con la información personal eliminada. Usa el siguiente código:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Este código guarda el documento con la información personal eliminada en un nuevo archivo.

### Ejemplo de código fuente para eliminar información personal usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo eliminar información personal de un documento usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede eliminar fácilmente información confidencial de sus propios documentos.