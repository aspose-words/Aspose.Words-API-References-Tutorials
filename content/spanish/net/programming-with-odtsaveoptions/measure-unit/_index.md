---
title: Unidad de medida
linktitle: Unidad de medida
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a especificar la unidad de medida al convertir un documento de Word a ODT con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-odtsaveoptions/measure-unit/
---

Cuando convierte un documento de Word al formato OpenDocument Text (ODT) en una aplicación C#, es posible que desee especificar la unidad de medida utilizada para el formato medible y las propiedades de contenido. Con la biblioteca Aspose.Words para .NET, puede especificar fácilmente esta funcionalidad utilizando las opciones de guardado de OdtSaveOptions. En esta guía paso a paso, le explicaremos cómo utilizar Aspose.Words para el código fuente .NET C# para convertir un documento de Word a ODT especificando la unidad de medida mediante OdtSaveOptions.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluido .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar formato, agregar secciones y mucho más.

## Cargando el documento de Word

El primer paso es cargar el documento de Word que desea convertir a ODT. Utilice la clase Documento para cargar el documento desde el archivo fuente. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

En este ejemplo, cargamos el documento "Document.docx" ubicado en el directorio de documentos.

## Configurar opciones de copia de seguridad

El siguiente paso es configurar las opciones de copia de seguridad para convertir a ODT. Utilice la clase OdtSaveOptions y establezca la propiedad MeasureUnit en el valor deseado. Por ejemplo, si desea utilizar pulgadas como unidad de medida, establezca MeasureUnit en OdtSaveMeasureUnit.Inches. He aquí cómo hacerlo:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Creamos un nuevo objeto OdtSaveOptions y configuramos la propiedad MeasureUnit en el valor deseado, en nuestro caso, OdtSaveMeasureUnit.Inches para usar pulgadas como unidad de medida.

## Convertir documento a ODT

Ahora que hemos configurado las opciones de guardar, podemos proceder a convertir el documento a ODT. Utilice el método Guardar de la clase Documento para guardar el documento convertido en formato ODT especificando opciones de guardado. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

En este ejemplo, guardamos el documento convertido como "WorkingWithOdtSaveOptions.MeasureUnit.odt" usando las opciones de guardado especificadas.

### Código fuente de ejemplo para OdtSaveOptions con funcionalidad "Unidad de medida" usando Aspose.Words para .NET



```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento de Word
Document doc = new Document(dataDir + "Document.docx");

// Configuración de opciones de respaldo con la función "Unidad de medida"
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Convertir el documento a ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusión

En esta guía, explicamos cómo convertir un documento de Word a ODT especificando la unidad de medida usando las opciones de guardado de OdtSaveOptions con la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y utiliza el código fuente de C# proporcionado, puede aplicar fácilmente esta funcionalidad en su aplicación C#. Especificar la unidad de medida al convertir a ODT le permite controlar el formato y las dimensiones del documento resultante de acuerdo con sus necesidades específicas.