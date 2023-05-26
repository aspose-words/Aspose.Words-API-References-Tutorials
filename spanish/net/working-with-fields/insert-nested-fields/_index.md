---
title: Insertar campos anidados
linktitle: Insertar campos anidados
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar fácilmente campos anidados en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-nested-fields/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Insertar campos anidados" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear el Documento y DocumentBuilder

Comenzamos creando un nuevo documento e inicializando un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar saltos de página

Usamos un bucle para insertar múltiples saltos de página en el documento.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Paso 4: Mover al pie de página

 usamos el`MoveToHeaderFooter()` del DocumentBuilder para mover el cursor al pie de página principal.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Paso 5: Insertar el campo anidado

 Usamos el DocumentBuilder`InsertField()` para insertar un campo anidado en el pie de página.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo de código fuente para insertar campos anidados con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar saltos de página.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Mover al pie de página.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Insertar campo anidado.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Actualice el campo.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos saltos de página, movimos el cursor al pie de página y luego insertamos un campo anidado en el pie de página.