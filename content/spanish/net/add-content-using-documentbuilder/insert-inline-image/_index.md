---
title: Insertar imagen en línea en un documento de Word
linktitle: Insertar imagen en línea en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar imágenes en línea en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-inline-image/
---
En este completo tutorial, aprenderá cómo insertar imágenes en línea en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar imágenes directamente al texto de sus documentos.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: crear un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Documento e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Insertar una imagen en línea
A continuación, utilice el método InsertImage de la clase DocumentBuilder para insertar una imagen en línea en el documento. Proporcione la ruta del archivo de imagen como parámetro:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Paso 3: guarde el documento
Después de insertar la imagen en línea, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Ejemplo de código fuente para insertar una imagen en línea usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar una imagen en línea usando Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar imágenes en línea en un documento de Word usando Aspose.Words para .NET. Si sigue la guía paso a paso y utiliza el código fuente proporcionado, ahora puede agregar imágenes sin problemas dentro del texto de sus documentos.

Las imágenes en línea son útiles para diversos escenarios, como agregar ilustraciones, logotipos u otros elementos visuales directamente al flujo del documento.

### Preguntas frecuentes para insertar una imagen en línea en un documento de Word

#### P: ¿Puedo cambiar el tamaño de las imágenes en línea dentro del documento de Word?

R: Sí, puede cambiar el tamaño de las imágenes en línea usando Aspose.Words para .NET. Después de insertar la imagen, puede manipular su tamaño ajustando las propiedades de ancho y alto del objeto Forma que representa la imagen.

#### P: ¿Es posible agregar texto alternativo a las imágenes en línea por motivos de accesibilidad?

R: Sí, puedes agregar texto alternativo a las imágenes en línea para mejorar la accesibilidad. Aspose.Words para .NET admite la adición de texto alternativo a las imágenes, lo que permite a los lectores de pantalla y otras tecnologías de asistencia describir el contenido de la imagen a los usuarios con discapacidad visual.

#### P: ¿Puedo aplicar formato o estilos a las imágenes en línea?

R: ¡Absolutamente! Aspose.Words para .NET proporciona amplias opciones de formato para imágenes en línea. Puede aplicar varios estilos, bordes, efectos y otros atributos de formato a las imágenes para que coincidan con el diseño visual de su documento.

#### P: ¿Aspose.Words para .NET admite la inserción de imágenes desde una secuencia o matriz de bytes?

R: Sí, puede insertar imágenes en línea desde secuencias o matrices de bytes usando Aspose.Words para .NET. Esto le permite trabajar con imágenes cargadas desde fuentes externas o imágenes generadas dinámicamente.

#### P: ¿Puedo insertar imágenes en posiciones específicas dentro del contenido del texto?

R: Sí, la clase DocumentBuilder en Aspose.Words para .NET proporciona un control preciso sobre la posición de inserción de imágenes en línea. Puede especificar la ubicación exacta dentro del texto donde se debe insertar la imagen.