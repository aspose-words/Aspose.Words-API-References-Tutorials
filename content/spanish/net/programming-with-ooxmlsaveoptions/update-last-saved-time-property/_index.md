---
title: Actualizar la propiedad de la última hora guardada
linktitle: Actualizar la propiedad de la última hora guardada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo actualizar automáticamente la propiedad Última hora guardada al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
En este tutorial, exploraremos el código fuente de C# proporcionado para actualizar la propiedad de la última hora de guardado al guardar un documento usando Aspose.Words para .NET. Esta característica le permite actualizar automáticamente la propiedad de la última hora de guardado del documento generado.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: configurar las opciones de copia de seguridad de OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 En este paso, configuramos las opciones de guardado de OOXML usando el`OoxmlSaveOptions` clase. Habilitamos la actualización automática de la propiedad de la última hora guardada configurando`UpdateLastSavedTimeProperty` a`true`.

## Paso 4: guarde el documento con la propiedad actualizada

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 En este último paso guardamos el documento utilizando el`Save` método y pasando la ruta al archivo de salida con el`.docx` extensión, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para actualizar automáticamente la propiedad de la última hora de guardado al guardar un documento. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Código fuente de muestra para actualizar la propiedad de la última hora guardada usando Aspose.Words para .NET 

```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusión

En este tutorial, exploramos la función de actualizar automáticamente la propiedad de la última hora de guardado al guardar un documento usando Aspose.Words para .NET. Al habilitar esta función con las opciones de guardado de OOXML, puede asegurarse de que la propiedad de la última hora de guardado se actualice automáticamente en el documento generado.

Actualizar la propiedad de hora del último guardado puede resultar útil para realizar un seguimiento de los cambios y las versiones de un documento. También realiza un seguimiento de cuándo se guardó el documento por última vez, lo que puede resultar útil en varios escenarios.

Aspose.Words para .NET facilita la actualización automática de la propiedad Hora de la última copia de seguridad al proporcionar opciones de copia de seguridad potentes y flexibles. Puede integrar esta función en sus proyectos para garantizar que los documentos generados tengan información de respaldo precisa.