---
title: Insertar campo TOA sin generador de documentos
linktitle: Insertar campo TOA sin generador de documentos
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar un campo TOA sin utilizar un generador de documentos en Aspose.Words para .NET. Siga nuestra guía paso a paso para gestionar eficientemente las citaciones legales.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-toafield-without-document-builder/
---
## Introducción

Crear un campo de Tabla de autoridades (TOA) en un documento de Word puede parecer como armar un rompecabezas complejo. Sin embargo, con la ayuda de Aspose.Words para .NET, el proceso se vuelve sencillo y sencillo. En este artículo, lo guiaremos a través de los pasos para insertar un campo TOA sin usar un generador de documentos, lo que le facilitará la administración de sus citas y referencias legales dentro de sus documentos de Word.

## Requisitos previos

Antes de sumergirnos en el tutorial, cubramos los elementos esenciales que necesitará:

-  Aspose.Words para .NET: asegúrese de tener instalada la última versión. Puedes descargarlo desde el[Aspose sitio web](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: un IDE compatible con .NET como Visual Studio.
- Conocimientos básicos de C#: será útil comprender la sintaxis y los conceptos básicos de C#.
- Documento de Word de muestra: cree o tenga listo un documento de muestra donde desee insertar el campo TOA.

## Importar espacios de nombres

Para comenzar, deberá importar los espacios de nombres necesarios de la biblioteca Aspose.Words. Esta configuración garantiza que tenga acceso a todas las clases y métodos necesarios para la manipulación de documentos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Dividamos el proceso en pasos simples y fáciles de seguir. Lo guiaremos a través de cada etapa, explicando qué hace cada fragmento de código y cómo contribuye a crear el campo TOA.

## Paso 1: Inicializar el documento

 Primero, necesita crear una instancia del`Document` clase. Este objeto representa el documento de Word en el que estás trabajando.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Este código inicializa un nuevo documento de Word. Puedes considerarlo como crear un lienzo en blanco al que agregarás tu contenido.

## Paso 2: crear y configurar el campo TA

A continuación, agregaremos un campo TA (Tabla de autoridades). Este campo marca las entradas que aparecerán en el TOA.

```csharp
Paragraph para = new Paragraph(doc);

// Queremos insertar campos TA y TOA como este:
// { TA \c 1 \l "Valor 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Aquí hay un desglose:
- Párrafo para = nuevo párrafo(doc);: Crea un nuevo párrafo dentro del documento.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: Agrega un campo TA al párrafo. El`FieldType.FieldTOAEntry` especifica que este es un campo de entrada TOA.
- fieldTA.EntryCategory = "1";: Establece la categoría de entrada. Esto es útil para categorizar diferentes tipos de entradas.
- fieldTA.LongCitation = "Valor 0";: Especifica el texto largo de la cita. Este es el texto que aparecerá en el TOA.
- doc.FirstSection.Body.AppendChild(para);: Agrega el párrafo con el campo TA al cuerpo del documento.

## Paso 3: agregue el campo TOA

Ahora, insertaremos el campo TOA real que compila todas las entradas TA en una tabla.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

En este paso:
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Agrega un campo TOA al párrafo.
- fieldToa.EntryCategory = "1";: Filtra las entradas para incluir solo aquellas marcadas con la categoría "1".

## Paso 4: actualice el campo TOA

Después de insertar el campo TOA, debe actualizarlo para asegurarse de que refleje las últimas entradas.

```csharp
fieldToa.Update();
```

Este comando actualiza el campo TOA, asegurando que todas las entradas marcadas se muestren correctamente en la tabla.

## Paso 5: guarde el documento

Finalmente, guarde su documento con el campo TOA recién agregado.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Esta línea de código guarda el documento en el directorio especificado. Asegúrate de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde desea guardar su archivo.

## Conclusión

¡Y ahí lo tienes! Ha agregado con éxito un campo TOA a un documento de Word sin utilizar un generador de documentos. Si sigue estos pasos, podrá gestionar citaciones de manera eficiente y crear tablas completas de autoridades en sus documentos legales. Aspose.Words para .NET hace que este proceso sea fluido y eficiente, brindándole las herramientas para manejar tareas de documentos complejas con facilidad.

## Preguntas frecuentes

### ¿Puedo agregar varios campos TA con diferentes categorías?
 Sí, puede agregar múltiples campos TA con diferentes categorías configurando el`EntryCategory`propiedad en consecuencia.

### ¿Cómo puedo personalizar la apariencia del TOA?
Puede personalizar la apariencia del TOA modificando las propiedades del campo TOA, como el formato de entrada y las etiquetas de categoría.

### ¿Es posible actualizar el campo TOA automáticamente?
 Si bien puede actualizar manualmente el campo TOA usando el`Update` método, Aspose.Words actualmente no admite actualizaciones automáticas sobre cambios en documentos.

### ¿Puedo agregar campos TA mediante programación en partes específicas del documento?
Sí, puede agregar campos TA en ubicaciones específicas insertándolos en los párrafos o secciones deseados.

### ¿Cómo manejo múltiples campos TOA en un solo documento?
 Puede administrar múltiples campos TOA asignando diferentes`EntryCategory` valores y garantizar que cada campo TOA filtre las entradas según su categoría.