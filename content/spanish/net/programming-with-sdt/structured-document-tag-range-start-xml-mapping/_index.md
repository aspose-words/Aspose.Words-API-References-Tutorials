---
title: Asignación Xml de inicio de rango de etiquetas de documento estructurado
linktitle: Asignación Xml de inicio de rango de etiquetas de documento estructurado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a vincular dinámicamente datos XML a etiquetas de documentos estructurados en Word usando Aspose.Words para .NET. Sigue nuestra guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## Introducción

¿Alguna vez ha querido insertar dinámicamente datos XML en un documento de Word? ¡Pues estás de suerte! Aspose.Words para .NET hace que esta tarea sea muy sencilla. En este tutorial, profundizaremos en el mapeo XML de inicio del rango de etiquetas de documentos estructurados. Esta característica le permite vincular partes XML personalizadas a controles de contenido, asegurando que el contenido de su documento se actualice perfectamente con sus datos XML. Listo para transformar sus documentos en obras maestras dinámicas.

## Requisitos previos

Antes de pasar a la parte de codificación, asegurémonos de tener todo lo que necesita:

1.  Aspose.Words para la biblioteca .NET: asegúrese de tener la última versión. Puedes descargarlo[aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: Visual Studio o cualquier otro IDE que admita C#.
3. Conocimientos básicos de C#: Es imprescindible estar familiarizado con la programación en C#.
4. Documento de Word: un documento de Word de muestra con el que trabajar.

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios. Esto garantizará que tengamos acceso a todas las clases y métodos necesarios en Aspose.Words para .NET.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## Paso 1: configure su directorio de documentos

Todo proyecto necesita una base, ¿verdad? Aquí, configuramos la ruta a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento de Word

A continuación, cargamos el documento de Word. Este es el documento donde insertaremos nuestros datos XML.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## Paso 3: agregar parte XML personalizada

Necesitamos construir una parte XML que contenga los datos que queremos insertar y agregarla a la colección CustomXmlPart del documento. Esta parte XML personalizada servirá como fuente de datos para nuestras etiquetas de documentos estructurados.

### Crear una parte XML

Primero, genere una identificación única para la parte XML y defina su contenido.

```csharp
// Construya una parte XML que contenga datos y agréguela a la colección CustomXmlPart del documento.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### Verificar el contenido del elemento XML

Para asegurarnos de que la parte XML se agregue correctamente, imprimimos su contenido.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## Paso 4: cree una etiqueta de documento estructurado

Una etiqueta de documento estructurado (SDT) es un control de contenido que puede vincularse a una parte XML. Aquí, creamos un SDT que mostrará el contenido de nuestra parte XML personalizada.

Primero, ubique el inicio del rango SDT en el documento.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Paso 5: configurar la asignación XML para SDT

Ahora es el momento de vincular nuestra parte XML al SDT. Al configurar una asignación XML, especificamos qué parte de los datos XML deben mostrarse en el SDT.

 El XPath apunta al elemento específico en la parte XML que queremos mostrar. Aquí señalamos el segundo`<text>` elemento dentro del`<root>` elemento.

```csharp
// Establecer una asignación para nuestra StructuredDocumentTag
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Paso 6: guarde el documento

Finalmente, guarde el documento para ver los cambios en acción. La SDT en el documento de Word ahora mostrará el contenido XML especificado.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Conclusión

¡Y ahí lo tienes! Ha asignado con éxito una parte XML a una etiqueta de documento estructurado en un documento de Word usando Aspose.Words para .NET. Esta poderosa característica le permite crear documentos dinámicos y basados en datos sin esfuerzo. Ya sea que esté generando informes, facturas o cualquier otro tipo de documento, el mapeo XML puede optimizar significativamente su flujo de trabajo.

## Preguntas frecuentes

### ¿Qué es una etiqueta de documento estructurado en Word?
Las etiquetas de documentos estructurados, también conocidas como controles de contenido, son contenedores para tipos específicos de contenido en documentos de Word. Se pueden utilizar para vincular datos, restringir la edición o guiar a los usuarios en la creación de documentos.

### ¿Cómo puedo actualizar dinámicamente el contenido de la pieza XML?
 Puede actualizar el contenido del elemento XML modificando el`xmlPartContent` cadena antes de agregarla al documento. Simplemente actualice la cadena con los nuevos datos y agréguela al`CustomXmlParts` recopilación.

### ¿Puedo vincular varias partes XML a diferentes SDT en el mismo documento?
Sí, puede vincular varias partes XML a diferentes SDT en el mismo documento. Cada SDT puede tener su propia parte XML y mapeo XPath exclusivos.

### ¿Es posible asignar estructuras XML complejas a SDT?
¡Absolutamente! Puede asignar estructuras XML complejas a SDT utilizando expresiones XPath detalladas que apunten con precisión a los elementos deseados dentro de la parte XML.

### ¿Cómo puedo eliminar una parte XML de un documento?
 Puede eliminar una parte XML llamando al`Remove` método en el`CustomXmlParts` recogida, pasando el`xmlPartId` de la parte XML que desea eliminar.