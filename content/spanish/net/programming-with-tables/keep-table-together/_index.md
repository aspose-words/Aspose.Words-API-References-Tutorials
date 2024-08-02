---
title: Mantenga la mesa unida
linktitle: Mantenga la mesa unida
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo evitar que las tablas se divida entre páginas en documentos de Word usando Aspose.Words para .NET. Siga nuestra guía para mantener documentos profesionales y legibles.
type: docs
weight: 10
url: /es/net/programming-with-tables/keep-table-together/
---
## Introducción

¿Alguna vez te has sentido frustrado cuando una tabla de tu documento de Word se divide en dos páginas? ¡Es como si su información cuidadosamente presentada decidiera de repente tomarse un descanso a mitad de camino! Mantener las tablas juntas en una página es crucial para la legibilidad y la presentación. Ya sea para un informe, una propuesta de proyecto o simplemente un documento personal, tener tablas divididas puede resultar bastante discordante. Por suerte para nosotros, Aspose.Words para .NET tiene una manera ingeniosa de resolver este problema. En este tutorial, seguiremos los pasos para mantener sus tablas intactas y con un aspecto impecable. ¡Vamos a sumergirnos!

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1.  Aspose.Words para .NET: si aún no lo ha instalado, puede descargarlo desde[aquí](https://releases.aspose.com/words/net/).
2. Un documento de Word con una tabla: trabajaremos con un documento de muestra que tiene una tabla que abarca varias páginas.
3. Conocimientos básicos de C#: este tutorial asume que tienes conocimientos básicos de programación en C#.

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios. Esto nos dará acceso a las clases y métodos que necesitamos de Aspose.Words para .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Dividamos el proceso en pasos fáciles y digeribles. Comenzaremos cargando nuestro documento y terminaremos guardando el documento actualizado donde la tabla permanece junta.

## Paso 1: cargue el documento

 Para trabajar con un documento de Word, primero debemos cargarlo. Usaremos el`Document` clase para esto.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Paso 2: accede a la mesa

A continuación, debemos conseguir la mesa que queremos mantener junta. Asumiremos que es la primera tabla del documento.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Paso 3: configure KeepWithNext para los párrafos

 Para evitar que la tabla se divida en varias páginas, debemos configurar el`KeepWithNext` propiedad para cada párrafo de la tabla, excepto los últimos párrafos de la última fila.

```csharp
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
    cell.EnsureMinimum();
    foreach (Paragraph para in cell.Paragraphs)
    {
        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }
}
```

## Paso 4: guarde el documento

Finalmente guardamos el documento actualizado. Esto aplicará nuestros cambios y garantizará que la tabla permanezca junta en una página.

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusión

¡Y ahí lo tienes! Con sólo unas pocas líneas de código, puede evitar que las tablas se divida en páginas de sus documentos de Word. Esta solución sencilla pero eficaz garantiza que sus tablas se mantengan limpias y profesionales, mejorando la legibilidad de sus documentos. Aspose.Words para .NET facilita el manejo de estos problemas de formato, permitiéndole concentrarse en crear contenido excelente.

## Preguntas frecuentes

### ¿Puedo mantener varias tablas juntas usando este método?  
Sí, puede aplicar la misma lógica a varias tablas recorriendo cada tabla de su documento.

### ¿Qué pasa si mi tabla es demasiado grande para caber en una página?  
Si una tabla es demasiado grande para caber en una sola página, aún abarcará varias páginas. Este método garantiza que las mesas más pequeñas permanezcan intactas sin dividirse.

### ¿Hay alguna manera de automatizar esto para todas las tablas de un documento?  
 Sí, puede recorrer todas las tablas de su documento y aplicar la`KeepWithNext` propiedad a cada párrafo.

### ¿Necesito una licencia paga de Aspose.Words para .NET?  
Puedes comenzar con una prueba gratuita desde[aquí](https://releases.aspose.com/), pero para una funcionalidad completa, se recomienda una licencia paga.

### ¿Puedo aplicar otro formato a la tabla mientras la mantengo unida?  
¡Absolutamente! Puede formatear su tabla según sea necesario mientras se asegura de que permanezca junta en una página.