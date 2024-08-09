---
title: Exportar a Markdown con alineación del contenido de la tabla
linktitle: Exportar a Markdown con alineación del contenido de la tabla
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a exportar documentos de Word a Markdown con tablas alineadas usando Aspose.Words para .NET. Siga nuestra guía paso a paso para obtener tablas Markdown perfectas.
type: docs
weight: 10
url: /es/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## Introducción

¡Hola! ¿Alguna vez te has preguntado cómo exportar tu documento de Word al formato Markdown con tablas perfectamente alineadas? Si eres un desarrollador que trabaja en documentación o simplemente alguien que ama Markdown, esta guía es para ti. Nos sumergiremos en el meollo de la cuestión del uso de Aspose.Words para .NET para lograr esto. ¿Listo para convertir sus tablas de Word en tablas de Markdown perfectamente alineadas? ¡Empecemos!

## Requisitos previos

Antes de profundizar en el código, hay algunas cosas que deberá implementar:

1.  Biblioteca Aspose.Words para .NET: asegúrese de tener la biblioteca Aspose.Words para .NET. Puedes descargarlo desde el[Página de lanzamientos de Aspose](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: configure su entorno de desarrollo. Visual Studio es una opción popular para el desarrollo .NET.
3. Conocimientos básicos de C#: comprender C# es esencial ya que escribiremos código en este lenguaje.
4. Documento de Word de muestra: tenga un documento de Word que pueda utilizar para realizar pruebas.

## Importar espacios de nombres

Antes de comenzar a codificar, importemos los espacios de nombres necesarios. Estos nos darán acceso a las clases y métodos de Aspose.Words que usaremos.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: Inicializar documento y DocumentBuilder

Primero lo primero, necesitamos crear un nuevo documento de Word e inicializar un`DocumentBuilder` objeto para comenzar a construir nuestro documento.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un nuevo documento.
Document doc = new Document();

// Inicialice DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: insertar celdas y alinear contenido

A continuación, insertaremos algunas celdas en nuestro documento y estableceremos su alineación. Esto es crucial para garantizar que la exportación de Markdown mantenga la alineación correcta.

```csharp
// Inserte una celda y establezca la alineación a la derecha.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// Inserte otra celda y establezca la alineación en el centro.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## Paso 3: Establecer la alineación del contenido de la tabla para la exportación de Markdown

 Ahora es el momento de configurar el`MarkdownSaveOptions` para controlar la alineación del contenido de la tabla en el archivo Markdown exportado. Guardaremos el documento con diferentes configuraciones de alineación para ver cómo funciona.

```csharp
// Cree el objeto MarkdownSaveOptions.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// Guarde el documento con alineación a la izquierda.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// Cambie la alineación a la derecha y guarde.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// Cambie la alineación al centro y guarde.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## Paso 4: utilice la alineación automática del contenido de la tabla

 El`Auto`La opción de alineación toma la alineación del primer párrafo en la columna de la tabla correspondiente. Esto puede resultar útil cuando tiene alineaciones mixtas en una sola tabla.

```csharp
// Establezca la alineación en Auto.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// Guarde el documento con alineación automática.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## Conclusión

¡Y ahí lo tienes! Exportar documentos de Word a Markdown con tablas alineadas usando Aspose.Words para .NET es muy sencillo una vez que sabes cómo hacerlo. Esta poderosa biblioteca facilita el control del formato y la alineación de sus tablas, asegurando que sus documentos Markdown tengan el aspecto que usted desea. ¡Feliz codificación!

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca que permite a los desarrolladores crear, modificar, convertir y exportar documentos de Word mediante programación.

### ¿Puedo establecer diferentes alineaciones para diferentes columnas en la misma tabla?
 Sí, usando el`Auto` opción de alineación, puede tener diferentes alineaciones según el primer párrafo de cada columna.

### ¿Necesito una licencia para usar Aspose.Words para .NET?
 Sí, Aspose.Words para .NET requiere una licencia para su funcionalidad completa. Puedes conseguir un[licencia temporal](https://purchase.aspose.com/temporary-license/) para evaluación.

### ¿Es posible exportar otros elementos del documento a Markdown usando Aspose.Words?
Sí, Aspose.Words admite la exportación de varios elementos como encabezados, listas e imágenes al formato Markdown.

### ¿Dónde puedo obtener asistencia si tengo problemas?
 Puede obtener apoyo del[Foro de soporte de Aspose.Words](https://forum.aspose.com/c/words/8).
