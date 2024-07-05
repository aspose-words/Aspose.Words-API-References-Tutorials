---
title: Uso de etiquetas de documentos estructurados (SDT) en Aspose.Words para Java
linktitle: Uso de etiquetas de documentos estructurados (SDT)
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a utilizar etiquetas de documentos estructurados (SDT) en Aspose.Words para Java con esta guía completa. Cree, modifique y vincule SDT a datos XML personalizados.
type: docs
weight: 19
url: /es/java/document-manipulation/using-structured-document-tags/
---

## Introducción al uso de etiquetas de documentos estructurados (SDT) en Aspose.Words para Java

Las etiquetas de documentos estructurados (SDT) son una característica poderosa de Aspose.Words para Java que le permite crear y manipular contenido estructurado dentro de sus documentos. En esta guía completa, lo guiaremos a través de los diversos aspectos del uso de SDT en Aspose.Words para Java. Ya sea un principiante o un desarrollador experimentado, encontrará información valiosa y ejemplos prácticos en este artículo.

## Empezando

Antes de profundizar en los detalles, configuremos nuestro entorno y creemos un SDT básico. En esta sección, cubriremos los siguientes temas:

- Creando un nuevo documento
- Agregar una etiqueta de documento estructurado
- Guardando el documento

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Cree una etiqueta de documento estructurado de tipo CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// guardar el documento
doc.save("WorkingWithSDT.docx");
```

## Comprobar el estado actual de una casilla de verificación SDT

Una vez que haya agregado una casilla de verificación SDT a su documento, es posible que desee verificar su estado actual mediante programación. Esto puede resultar útil cuando necesita validar la entrada del usuario o realizar acciones específicas según el estado de la casilla de verificación.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // La casilla de verificación está marcada
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Modificar controles de contenido

En esta sección, exploraremos cómo modificar los controles de contenido dentro de su documento. Cubriremos tres tipos de controles de contenido: texto sin formato, lista desplegable e imagen.

### Modificación del control de contenido de texto sin formato

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Borrar el contenido existente
    sdtPlainText.removeAllChildren();

    // Agregar nuevo texto
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Modificación del control de contenido de la lista desplegable

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Seleccione el segundo elemento de la lista.
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Modificación del control del contenido de la imagen

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Reemplace la imagen por una nueva.
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Crear un control de contenido ComboBox

Un control de contenido ComboBox permite a los usuarios seleccionar de una lista predefinida de opciones. Creemos uno en nuestro documento.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Trabajar con control de contenido de texto enriquecido

Los controles de contenido de texto enriquecido son perfectos para agregar texto formateado a sus documentos. Creemos uno y establezcamos su contenido.

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## Configuración de estilos de control de contenido

Puede aplicar estilos a los controles de contenido para mejorar la apariencia visual de su documento. Veamos cómo configurar el estilo de un control de contenido.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Aplicar un estilo personalizado
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Vincular un SDT a datos XML personalizados

En algunos escenarios, es posible que necesite vincular un SDT a datos XML personalizados para la generación de contenido dinámico. Exploremos cómo lograrlo.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Crear una tabla con secciones repetidas asignadas a datos XML personalizados

Las tablas con secciones repetidas pueden resultar extremadamente útiles para presentar datos estructurados. Creemos una tabla de este tipo y asignemosla a datos XML personalizados.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## Trabajar con etiquetas de documentos estructurados de varias secciones

Las etiquetas de documentos estructurados pueden abarcar varias secciones de un documento. En esta sección, exploraremos cómo trabajar con SDT de varias secciones.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Conclusión

Las etiquetas de documentos estructurados en Aspose.Words para Java proporcionan una forma versátil de administrar y formatear el contenido de sus documentos. Ya sea que necesite crear plantillas, formularios o documentos dinámicos, los SDT ofrecen la flexibilidad y el control que necesita. Si sigue los ejemplos y pautas proporcionados en este artículo, puede aprovechar el poder de los SDT para mejorar sus tareas de procesamiento de documentos.

## Preguntas frecuentes

### ¿Cuál es el propósito de las etiquetas de documentos estructurados (SDT)?

Las etiquetas de documentos estructurados (SDT) sirven para organizar y formatear el contenido dentro de los documentos, lo que facilita la creación de plantillas, formularios y documentos estructurados.

### ¿Cómo puedo comprobar el estado actual de un SDT de casilla de verificación?

 Puede verificar el estado actual de un SDT de casilla de verificación usando el`setChecked` método, como se demuestra en el artículo.

### ¿Puedo aplicar estilos a los controles de contenido?

Sí, puede aplicar estilos a los controles de contenido para personalizar su apariencia en el documento.

### ¿Es posible vincular un SDT a datos XML personalizados?

Sí, puede vincular un SDT a datos XML personalizados, lo que permite la generación de contenido dinámico y el mapeo de datos.

### ¿Qué son las secciones repetidas en los SDT?

Las secciones repetidas en SDT le permiten crear tablas con datos dinámicos, donde las filas se pueden repetir en función de los datos XML asignados.