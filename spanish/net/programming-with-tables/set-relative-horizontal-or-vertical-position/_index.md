---
title: Establecer la posición horizontal o vertical relativa
linktitle: Establecer la posición horizontal o vertical relativa
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a establecer la posición horizontal o vertical relativa de una tabla en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

En este tutorial, vamos a aprender cómo establecer la posición horizontal o vertical relativa de una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá establecer la posición horizontal o vertical relativa de su tabla en sus documentos de Word.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento
Para iniciar el procesamiento de textos con el documento, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos y proporcione el nombre de archivo correcto.

## Paso 3: Configuración de la posición relativa de la mesa
A continuación, estableceremos la posición horizontal o vertical relativa de la mesa. Usa el siguiente código:

```csharp
// recuperar la mesa
Table table = doc.FirstSection.Body.Tables[0];

//Definición de la posición horizontal relativa de la mesa
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definir la posición vertical relativa de la mesa
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Aquí usamos el documento para recuperar la primera tabla del cuerpo de la primera sección. A continuación, establecemos la posición horizontal relativa de la mesa con el`HorizontalAnchor` propiedad usando el`RelativeHorizontalPosition.Column` valor. De manera similar, establecemos la posición vertical relativa de la mesa con el`VerticalAnchor` propiedad usando el`RelativeVerticalPosition.Page` valor.

## Paso 4: Guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con la posición relativa de la tabla definida. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para establecer la posición horizontal o vertical relativa usando Aspose.Words para .NET 

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
En este tutorial, aprendimos cómo establecer la posición horizontal o vertical relativa de una tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede aplicar esta posición relativa a sus tablas en sus documentos de Word.