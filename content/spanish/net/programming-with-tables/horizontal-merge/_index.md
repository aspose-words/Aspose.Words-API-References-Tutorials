---
title: Fusión horizontal
linktitle: Fusión horizontal
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo fusionar celdas horizontalmente en un documento de Word usando Aspose.Words para .NET con este tutorial detallado paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-tables/horizontal-merge/
---
## Introducción

¡Hola! ¿Listo para sumergirte en el mundo de Aspose.Words para .NET? Hoy vamos a abordar una característica muy útil: la combinación horizontal de tablas. Esto puede sonar un poco técnico, pero no te preocupes, te cubro las espaldas. Al final de este tutorial, serás un profesional en la combinación de celdas en tus documentos de Word mediante programación. Entonces, ¡arremanguémonos y comencemos!

## Requisitos previos

Antes de entrar en el meollo de la cuestión, hay algunas cosas que necesitará tener implementadas:

1. Biblioteca Aspose.Words para .NET: si aún no lo ha hecho, descargue la biblioteca Aspose.Words para .NET. puedes agarrarlo[aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo adecuado, como Visual Studio.
3. Conocimientos básicos de C#: Será beneficioso tener un conocimiento básico de la programación en C#.

Una vez que los haya ordenado, ¡estará listo para comenzar!

## Importar espacios de nombres

Antes de profundizar en el código, asegurémonos de haber importado los espacios de nombres necesarios. En su proyecto C#, asegúrese de incluir:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Muy bien, analicemos el proceso de fusionar horizontalmente celdas de una tabla en un documento de Word usando Aspose.Words para .NET.

## Paso 1: configurar su documento

 Primero lo primero, necesitamos crear un nuevo documento de Word e inicializar el`DocumentBuilder`:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Este fragmento de código configura un nuevo documento y prepara el`DocumentBuilder` Para acción.

## Paso 2: insertar la primera celda

A continuación, comenzamos insertando la primera celda y marcándola para fusión horizontal:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 Aquí, insertamos una nueva celda y configuramos su`HorizontalMerge`propiedad a`CellMerge.First`, lo que indica que esta celda es el comienzo de una secuencia de celdas fusionadas.

## Paso 3: insertar la celda combinada

Ahora, insertamos la celda que se fusionará con la anterior:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 Esta celda está configurada para fusionarse con la celda anterior usando`CellMerge.Previous` . Observe cómo terminamos la fila con`builder.EndRow()`.

## Paso 4: insertar celdas no fusionadas

Para ilustrar la diferencia, insertemos un par de celdas no fusionadas:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

Aquí, insertamos dos celdas sin fusión horizontal. Esto muestra cómo se comportan las celdas cuando no forman parte de una secuencia fusionada.

## Paso 5: terminar la mesa

Finalmente, finalizamos la tabla y guardamos el documento:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

Este fragmento de código completa la tabla y guarda el documento en el directorio especificado.

## Conclusión

¡Y ahí lo tienes! Acaba de dominar el arte de fusionar celdas horizontalmente en un documento de Word usando Aspose.Words para .NET. Si sigue estos pasos, podrá crear estructuras de tablas complejas con facilidad. Continúe experimentando y explorando las capacidades de Aspose.Words para hacer que sus documentos sean tan dinámicos y flexibles como necesite. ¡Feliz codificación!

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca que permite a los desarrolladores crear, editar y manipular documentos de Word mediante programación en aplicaciones .NET.

### ¿Puedo fusionar celdas verticalmente con Aspose.Words para .NET?
 Sí, también puedes fusionar celdas verticalmente usando el`CellFormat.VerticalMerge` propiedad.

### ¿Aspose.Words para .NET es de uso gratuito?
 Aspose.Words para .NET ofrece una prueba gratuita, pero para obtener una funcionalidad completa, deberá adquirir una licencia. Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).

### ¿Cómo puedo obtener más información sobre Aspose.Words para .NET?
 Puedes explorar la documentación detallada.[aquí](https://reference.aspose.com/words/net/).

### ¿Dónde puedo obtener soporte para Aspose.Words para .NET?
 Para cualquier consulta o problema, puede visitar el foro de soporte de Aspose.[aquí](https://forum.aspose.com/c/words/8).