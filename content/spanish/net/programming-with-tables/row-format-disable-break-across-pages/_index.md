---
title: Formato de fila Deshabilitar división entre páginas
linktitle: Formato de fila Deshabilitar división entre páginas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a deshabilitar los saltos de fila en las páginas de documentos de Word usando Aspose.Words para .NET para mantener la legibilidad y el formato de la tabla.
type: docs
weight: 10
url: /es/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Introducción

Al trabajar con tablas en documentos de Word, es posible que desee asegurarse de que las filas no se dividan en varias páginas, lo que puede ser esencial para mantener la legibilidad y el formato de sus documentos. Aspose.Words para .NET ofrece una manera sencilla de desactivar los saltos de fila en varias páginas.

En este tutorial, lo guiaremos a través del proceso de deshabilitar saltos de fila en las páginas de un documento de Word usando Aspose.Words para .NET.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Biblioteca Aspose.Words para .NET instalada.
- Un documento de Word con una tabla que ocupa varias páginas.

## Importar espacios de nombres

Primero, importe los espacios de nombres necesarios en su proyecto:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Paso 1: Cargue el documento

Cargue el documento que contiene la tabla que abarca varias páginas.

```csharp
// Ruta al directorio de su documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Paso 2: Acceda a la tabla

Acceda a la primera tabla del documento. Esto supone que la tabla que desea modificar es la primera tabla del documento.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Paso 3: Deshabilitar la división entre páginas para todas las filas

 Recorra cada fila de la tabla y establezca el`AllowBreakAcrossPages`propiedad a`false`Esto garantiza que las filas no se dividan en varias páginas.

```csharp
// Deshabilitar la división entre páginas para todas las filas de la tabla.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Paso 4: Guardar el documento

Guarde el documento modificado en el directorio especificado.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusión

En este tutorial, demostramos cómo deshabilitar los saltos de fila en las páginas de un documento de Word mediante Aspose.Words para .NET. Si sigue los pasos descritos anteriormente, podrá asegurarse de que las filas de la tabla permanezcan intactas y no se dividan en las páginas, lo que mantendrá la legibilidad y el formato del documento.

## Preguntas frecuentes

### ¿Puedo desactivar los saltos de fila en las páginas para una fila específica en lugar de para todas las filas?  
 Sí, puede deshabilitar los saltos de fila para filas específicas accediendo a la fila deseada y configurando su`AllowBreakAcrossPages`propiedad a`false`.

### ¿Este método funciona para tablas con celdas fusionadas?  
 Sí, este método funciona para tablas con celdas fusionadas. La propiedad`AllowBreakAcrossPages` se aplica a toda la fila, independientemente de la fusión de celdas.

### ¿Este método funcionará si la tabla está anidada dentro de otra tabla?  
Sí, puedes acceder a las tablas anidadas y modificarlas de la misma manera. Asegúrate de hacer referencia correctamente a la tabla anidada por su índice u otras propiedades.

### ¿Cómo puedo comprobar si una fila permite dividirse en varias páginas?  
 Puede comprobar si una fila permite dividirla en varias páginas accediendo a la`AllowBreakAcrossPages` propiedad de la`RowFormat` y comprobar su valor.

### ¿Hay alguna manera de aplicar esta configuración a todas las tablas de un documento?  
Sí, puede recorrer todas las tablas del documento y aplicar esta configuración a cada una de ellas.