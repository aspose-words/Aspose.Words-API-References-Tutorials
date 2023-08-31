---
title: Insertar regla horizontal en un documento de Word
linktitle: Insertar regla horizontal en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar reglas horizontales en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
En este ejemplo completo, aprenderá cómo insertar una regla horizontal en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar reglas horizontales a sus documentos para la separación y organización visual.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: crear un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Documento e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserta una regla horizontal
A continuación, use el método Writeln de la clase DocumentBuilder para agregar un texto descriptivo y luego inserte una regla horizontal:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Paso 3: guarde el documento
Después de insertar la regla horizontal, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Ejemplo de código fuente para insertar regla horizontal usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar una regla horizontal usando Aspose.Words para .NET:
Las reglas horizontales son útiles para diversos escenarios, como dividir secciones, crear pausas visuales o resaltar información importante.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos y mejorarlo con funciones adicionales según sea necesario.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar una regla horizontal en un documento de Word usando Aspose.Words para .NET. Si sigue la guía paso a paso y utiliza el código fuente proporcionado, ahora puede separar y organizar visualmente sus documentos usando reglas horizontales.

### Preguntas frecuentes para insertar regla horizontal en un documento de Word

#### P: ¿Puedo personalizar la apariencia de la regla horizontal?

R: ¡Sí, absolutamente! Aspose.Words para .NET proporciona varias propiedades para personalizar la apariencia de la regla horizontal. Puede ajustar su ancho, alto, alineación, color y sombreado para que coincida con la estética de su documento.

#### P: ¿Puedo agregar varias reglas horizontales en un solo documento?

R: ¡Ciertamente! Puede insertar tantas reglas horizontales como necesite en un documento de Word utilizando Aspose.Words para .NET. Simplemente repita el proceso de inserción para agregar múltiples saltos visuales o divisores de sección.

#### P: ¿Las reglas horizontales son compatibles con otros formatos de archivo, como PDF?

R: Sí, las reglas horizontales insertadas con Aspose.Words para .NET son compatibles con varios formatos de archivo, incluidos DOCX y PDF. Esto significa que puede exportar sus documentos en diferentes formatos manteniendo las reglas horizontales.

#### P: ¿Puedo insertar mediante programación una regla horizontal en posiciones específicas del documento?

R: ¡Absolutamente! Aspose.Words para .NET le permite colocar la regla horizontal en ubicaciones específicas dentro del documento mediante programación. Puede controlar su ubicación según el contenido y la estructura de su documento.

#### P: ¿Aspose.Words para .NET es adecuado tanto para aplicaciones web como de escritorio?

R: Sí, Aspose.Words para .NET es versátil y se puede utilizar tanto en aplicaciones web como de escritorio. Ya sea que esté creando una aplicación de Windows o un sistema basado en web, puede integrar la biblioteca sin esfuerzo.