---
title: Formato de fila Desactivar salto entre páginas
linktitle: Formato de fila Desactivar salto entre páginas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a deshabilitar los saltos de fila entre páginas en documentos de Word usando Aspose.Words para .NET para mantener la legibilidad y el formato de las tablas.
type: docs
weight: 10
url: /es/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Introducción

Cuando trabaje con tablas en documentos de Word, es posible que desee asegurarse de que las filas no se divida entre páginas, lo que puede ser esencial para mantener la legibilidad y el formato de sus documentos. Aspose.Words para .NET proporciona una forma sencilla de desactivar los saltos de fila entre páginas.

En este tutorial, lo guiaremos a través del proceso de deshabilitar los saltos de fila entre páginas en un documento de Word usando Aspose.Words para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada.
- Un documento de Word con una tabla que abarca varias páginas.

## Importar espacios de nombres

Primero, importe los espacios de nombres necesarios en su proyecto:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Paso 1: cargue el documento

Cargue el documento que contiene la tabla que abarca varias páginas.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Paso 2: accede a la mesa

Accede a la primera tabla del documento. Esto supone que la tabla que desea modificar es la primera tabla del documento.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Paso 3: deshabilite la división de páginas para todas las filas

 Recorra cada fila de la tabla y establezca el`AllowBreakAcrossPages`propiedad a`false`. Esto garantiza que las filas no se dividirán entre páginas.

```csharp
// Deshabilite la división de páginas para todas las filas de la tabla.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Paso 4: guarde el documento

Guarde el documento modificado en su directorio especificado.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusión

En este tutorial, demostramos cómo deshabilitar los saltos de fila entre páginas en un documento de Word usando Aspose.Words para .NET. Si sigue los pasos descritos anteriormente, puede asegurarse de que las filas de su tabla permanezcan intactas y no se divida en páginas, manteniendo la legibilidad y el formato del documento.

## Preguntas frecuentes

### ¿Puedo desactivar los saltos de fila entre páginas para una fila específica en lugar de para todas las filas?  
 Sí, puede desactivar los saltos de fila para filas específicas accediendo a la fila deseada y configurando su`AllowBreakAcrossPages`propiedad a`false`.

### ¿Este método funciona para tablas con celdas combinadas?  
 Sí, este método funciona para tablas con celdas combinadas. La propiedad`AllowBreakAcrossPages` se aplica a toda la fila, independientemente de la combinación de celdas.

### ¿Funcionará este método si la tabla está anidada dentro de otra tabla?  
Sí, puedes acceder y modificar tablas anidadas de la misma manera. Asegúrese de hacer referencia correctamente a la tabla anidada por su índice u otras propiedades.

### ¿Cómo puedo comprobar si una fila permite dividir páginas?  
 Puedes comprobar si una fila permite dividir páginas accediendo al`AllowBreakAcrossPages` propiedad de la`RowFormat` y comprobando su valor.

### ¿Hay alguna manera de aplicar esta configuración a todas las tablas de un documento?  
Sí, puede recorrer todas las tablas del documento y aplicar esta configuración a cada una.