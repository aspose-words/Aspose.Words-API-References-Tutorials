---
title: Actualizar última propiedad de hora guardada
linktitle: Actualizar última propiedad de hora guardada
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a actualizar automáticamente la propiedad Última hora guardada al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
En este tutorial, exploraremos el código fuente de C# provisto para actualizar la última propiedad de tiempo de guardado al guardar un documento usando Aspose.Words para .NET. Esta función le permite actualizar automáticamente la última propiedad de tiempo de guardado del documento generado.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: Configuración de las opciones de copia de seguridad de OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 En este paso, configuramos las opciones de guardado de OOXML usando el`OoxmlSaveOptions` clase. Habilitamos la actualización automática de la última propiedad de tiempo de guardado configurando`UpdateLastSavedTimeProperty` a`true`.

## Paso 4: Guarde el documento con la propiedad actualizada

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 En este último paso, guardamos el documento usando el`Save` y pasando la ruta al archivo de salida con el`.docx` extensión, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para actualizar automáticamente la última propiedad de tiempo de guardado al guardar un documento. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Ejemplo de código fuente para Actualizar la última propiedad de hora guardada usando Aspose.Words para .NET 

```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusión

En este tutorial, exploramos la característica de actualizar automáticamente la última propiedad de tiempo de guardado al guardar un documento usando Aspose.Words para .NET. Al habilitar esta función con las opciones de guardado de OOXML, puede asegurarse de que la última propiedad de tiempo de guardado se actualice automáticamente en el documento generado.

Actualizar la última propiedad de tiempo de guardado puede ser útil para realizar un seguimiento de los cambios y las versiones de un documento. También realiza un seguimiento de cuándo se guardó el documento por última vez, lo que puede ser útil en varios escenarios.

Aspose.Words para .NET facilita la actualización automática de la propiedad Hora de la última copia de seguridad al proporcionar opciones de copia de seguridad potentes y flexibles. Puede integrar esta función en sus proyectos para asegurarse de que los documentos generados tengan información de respaldo precisa.