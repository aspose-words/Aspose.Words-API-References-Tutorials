---
title: Insertar campo avanzado sin generador de documentos
linktitle: Insertar campo avanzado sin generador de documentos
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo insertar un campo avanzado en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Inserción avanzada de campos sin DocumentBuilder" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código proporcionado, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear el documento y el párrafo

Comenzamos creando un nuevo documento y buscando el primer párrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Paso 3: Insertar los campos avanzados

 Usamos el`AppendField()` Método para insertar un campo avanzado en el párrafo.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Luego configuramos las distintas propiedades del campo avanzado especificando los valores deseados.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Finalmente llamamos al`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo del código fuente para insertar un campo avanzado sin DocumentBuilder con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserte el campo avanzado.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo avanzado sin usar DocumentBuilder, configuramos las diversas propiedades del campo y guardamos el documento con un nombre de archivo específico.

Con esto concluye nuestra guía sobre cómo utilizar la función "Insertar campo avanzado sin DocumentBuilder" con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Qué es un campo avanzado en Aspose.Words?

R: Un campo avanzado en Aspose.Words es un tipo especial de campo que le permite realizar cálculos, incluir condiciones y realizar operaciones complejas en un documento de Word. Ofrece una gran flexibilidad para crear campos dinámicos y personalizados.

#### P: ¿Cómo insertar un campo avanzado en un documento de Word sin usar el Generador de documentos en Aspose.Words?

R: Para insertar un campo avanzado en un documento de Word sin usar el Generador de documentos en Aspose.Words, puede seguir estos pasos:

1. Importe la clase Documento y Campo desde el espacio de nombres Aspose.Words.Fields.
2. Cree una instancia de Documento cargando su documento existente.
3. Utilice el método InsertField para insertar un campo avanzado especificando el código del campo avanzado.
4. Guarde el documento.

#### P: ¿Cómo obtener el resultado de un campo avanzado en un documento de Word?

R: Para obtener el resultado de un campo avanzado en un documento de Word, puede usar la propiedad Resultado disponible en la clase Campo. Esta propiedad devuelve el resultado calculado del campo.

#### P: ¿Puedo modificar la fórmula de un campo avanzado después de insertarlo en un documento de Word?

R: Sí, puedes editar la fórmula de un campo avanzado después de insertarlo en un documento de Word. Puede hacer esto accediendo a la propiedad FieldCode de la clase Field y actualizando la fórmula modificando el texto de la fórmula.