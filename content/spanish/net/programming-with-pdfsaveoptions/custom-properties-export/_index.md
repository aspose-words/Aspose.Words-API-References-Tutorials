---
title: Exportar propiedades personalizadas en un documento PDF
linktitle: Exportar propiedades personalizadas en un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a exportar propiedades personalizadas al convertir documentos a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/custom-properties-export/
---

En este tutorial, lo guiaremos a través de los pasos para exportar las propiedades personalizadas de un documento en un documento PDF usando Aspose.Words para .NET. Exportar propiedades personalizadas le permite incluir información adicional en el documento PDF generado. Siga los pasos a continuación:

## Paso 1: crear un documento y agregar propiedades personalizadas

Comience creando una instancia de la clase Documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Paso 2: agregar propiedades personalizadas
 A continuación, agregue las propiedades personalizadas deseadas. Por ejemplo, para agregar una propiedad "Empresa" con el valor "Apose", use el`Add` método de la colección CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Puede agregar tantas propiedades personalizadas como sea necesario.

## Paso 3: configurar las opciones de exportación de PDF

Cree una instancia de la clase PdfSaveOptions y especifique cómo exportar propiedades personalizadas:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Esta opción controla la exportación de propiedades personalizadas al convertir a PDF.

## Paso 4: convertir documento a PDF

 Utilizar el`Save` Método para convertir el documento a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para exportación de propiedades personalizadas usando Aspose.Words para .NET

Aquí está el código fuente completo para exportar propiedades personalizadas de un documento usando Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Si sigue estos pasos, puede exportar fácilmente las propiedades personalizadas de un documento al convertirlo a PDF con Aspose.Words para .NET.


## Conclusión

En este tutorial, explicamos cómo exportar propiedades personalizadas de un documento a un documento PDF usando Aspose.Words para .NET. Si sigue los pasos descritos, puede incluir fácilmente información adicional en el documento PDF generado exportando las propiedades personalizadas del documento. Aproveche las funciones de Aspose.Words para .NET para personalizar y enriquecer sus documentos PDF exportando propiedades personalizadas.

### Preguntas frecuentes

#### P: ¿Qué es exportar propiedades personalizadas a un documento PDF?
R: Exportar propiedades personalizadas a un documento PDF permite incluir información adicional en el documento PDF generado. Las propiedades personalizadas son metadatos específicos de su documento, como etiquetas, palabras clave o credenciales. Al exportar estas propiedades personalizadas, puede ponerlas a disposición de los usuarios cuando vean el documento PDF.

#### P: ¿Cómo puedo exportar las propiedades personalizadas de un documento a un documento PDF usando Aspose.Words para .NET?
R: Para exportar las propiedades personalizadas de un documento a un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Crear una instancia del`Document` clase.

 Agregue las propiedades personalizadas deseadas usando el`CustomDocumentProperties` recopilación. Por ejemplo, utilice el`Add` Método para agregar una propiedad "Empresa" con el valor "Apose".

 Crear una instancia del`PdfSaveOptions` clase y especificar cómo exportar propiedades personalizadas utilizando el`CustomPropertiesExport` propiedad. El`PdfCustomPropertiesExport.Standard` value exporta propiedades personalizadas según la configuración predeterminada.

 Utilizar el`Save` método de la`Document` clase para convertir el documento a PDF especificando las opciones de conversión.

#### P: ¿Cómo puedo acceder a las propiedades personalizadas de un documento PDF?
R: Para acceder a las propiedades personalizadas de un documento PDF, puede utilizar un lector de PDF compatible que admita la visualización de las propiedades del documento. Los lectores de PDF más comunes, como Adobe Acrobat Reader, brindan acceso a metadatos y propiedades de un documento PDF. Por lo general, puedes encontrar estas opciones en el menú "Archivo" o haciendo clic derecho en el documento y seleccionando "Propiedades".