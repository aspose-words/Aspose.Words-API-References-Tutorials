---
title: Establecer posición relativa horizontal o vertical
linktitle: Establecer posición relativa horizontal o vertical
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar la posición relativa horizontal o vertical de una tabla en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

En este tutorial, aprenderemos cómo establecer la posición relativa horizontal o vertical de una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá establecer la posición relativa horizontal o vertical de su tabla en sus documentos de Word.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento
Para iniciar el procesamiento de textos con el documento, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos y proporcione el nombre de archivo correcto.

## Paso 3: establecer la posición relativa de la mesa
A continuación, estableceremos la posición horizontal o vertical relativa de la mesa. Utilice el siguiente código:

```csharp
// recuperar la mesa
Table table = doc.FirstSection.Body.Tables[0];

//Definición de la posición horizontal relativa de la mesa.
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definir la posición vertical relativa de la mesa.
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Aquí usamos el documento para recuperar la primera tabla del cuerpo de la primera sección. A continuación, establecemos la posición horizontal relativa de la mesa con el`HorizontalAnchor` propiedad utilizando el`RelativeHorizontalPosition.Column` valor. De manera similar, establecemos la posición vertical relativa de la mesa con el`VerticalAnchor` propiedad utilizando el`RelativeVerticalPosition.Page` valor.

## Paso 4: guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con la posición relativa de la tabla definida. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para establecer una posición horizontal o vertical relativa usando Aspose.Words para .NET 

```csharp
//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Conclusión
En este tutorial, aprendimos cómo establecer la posición relativa horizontal o vertical de una tabla en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede aplicar esta posición relativa a sus tablas en sus documentos de Word.