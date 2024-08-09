---
title: Usando formas de documento em Aspose.Words para Java
linktitle: Usando formas de documento
second_title: API de processamento de documentos Java Aspose.Words
description: Desbloqueie o poder das formas de documentos em Aspose.Words para Java. Aprenda a criar documentos visualmente envolventes com exemplos passo a passo.
type: docs
weight: 14
url: /pt/java/document-conversion-and-export/using-document-shapes/
---

## Introdução ao uso de formas de documentos em Aspose.Words para Java

Neste guia abrangente, mergulharemos no mundo das formas de documentos em Aspose.Words for Java. As formas são elementos essenciais quando se trata de criar documentos interativos e visualmente atraentes. Se você precisa adicionar textos explicativos, botões, imagens ou marcas d'água, Aspose.Words for Java fornece as ferramentas para fazer isso com eficiência. Vamos explorar como usar essas formas passo a passo com exemplos de código-fonte.

## Introdução às formas de documentos

 Antes de entrarmos no código, vamos configurar nosso ambiente. Certifique-se de ter o Aspose.Words for Java integrado ao seu projeto. Se ainda não o fez, você pode baixá-lo no site Aspose[Baixe Aspose.Words para Java](https://releases.aspose.com/words/java/)

## Adicionando formas a documentos

### Inserindo um GroupShape

 UM`GroupShape` permite agrupar várias formas. Veja como você pode criar e inserir um`GroupShape`:

```java
Document doc = new Document();
doc.ensureMinimum();

GroupShape groupShape = new GroupShape(doc);
Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1);
accentBorderShape.setWidth(100.0);
accentBorderShape.setHeight(100.0);

groupShape.appendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
actionButtonShape.setLeft(100.0);
actionButtonShape.setWidth(100.0);
actionButtonShape.setHeight(200.0);

groupShape.appendChild(actionButtonShape);

groupShape.setWidth(200.0);
groupShape.setHeight(200.0);
groupShape.setCoordSize(new Dimension(200, 200));

DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertNode(groupShape);

doc.save("Your Directory Path" + "WorkingWithShapes.AddGroupShape.docx");
```

### Inserindo um formato de caixa de texto

 Para inserir uma forma de caixa de texto, você pode usar o`insertShape` método conforme mostrado no exemplo abaixo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
    RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);

shape.setRotation(30.0);
builder.writeln();

shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
shape.setRotation(30.0);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);

doc.save("Your Directory Path" + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Manipulando Propriedades de Forma

### Gerenciando proporção de aspecto

Você pode controlar se a proporção de uma forma está bloqueada ou não. Veja como desbloquear a proporção de uma forma:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Colocando uma forma em uma célula de tabela

Se você precisar colocar uma forma dentro de uma célula da tabela, poderá fazer isso com o seguinte código:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.startTable();
builder.getRowFormat().setHeight(100.0);
builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);

for (int i = 0; i < 31; i++) {
    if (i != 0 && i % 7 == 0)
        builder.endRow();

    builder.insertCell();
    builder.write("Cell contents");
}

builder.endTable();

Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.isLayoutInCell(true); // Exiba a forma fora da célula da tabela se ela for colocada em uma célula.
watermark.setWidth(300.0);
watermark.setHeight(70.0);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setRotation(-40);
watermark.setFillColor(Color.GRAY);
watermark.setStrokeColor(Color.GRAY);
watermark.getTextPath().setText("watermarkText");
watermark.getTextPath().setFontFamily("Arial");
watermark.setName("WaterMark_{Guid.NewGuid()}");
watermark.setWrapType(WrapType.NONE);

Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
builder.moveTo(run);
builder.insertNode(watermark);

doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
doc.save("Your Directory Path" + "WorkingWithShapes.LayoutInCell.docx");
```

## Trabalhando com formas SmartArt

### Detectando formas SmartArt

Você pode detectar formas SmartArt em um documento usando o seguinte código:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### Atualizando desenhos SmartArt

Para atualizar desenhos SmartArt em um documento, use o seguinte código:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## Conclusão

Neste guia, exploramos o mundo das formas de documentos em Aspose.Words for Java. Você aprendeu como adicionar diversas formas aos seus documentos, manipular suas propriedades e trabalhar com formas SmartArt. Com esse conhecimento, você pode criar documentos interativos e visualmente atraentes com facilidade.

## Perguntas frequentes

### O que é Aspose.Words para Java?

Aspose.Words for Java é uma biblioteca Java que permite aos desenvolvedores criar, modificar e converter documentos do Word programaticamente. Ele oferece uma ampla gama de recursos e ferramentas para trabalhar com documentos em vários formatos.

### Como posso baixar Aspose.Words para Java?

 Você pode baixar Aspose.Words for Java do site Aspose seguindo este link:[Baixe Aspose.Words para Java](https://releases.aspose.com/words/java/)

### Quais são os benefícios de usar formatos de documentos?

As formas dos documentos adicionam elementos visuais e interatividade aos seus documentos, tornando-os mais envolventes e informativos. Com formas, você pode criar textos explicativos, botões, imagens, marcas d'água e muito mais, aprimorando a experiência geral do usuário.

### Posso personalizar a aparência das formas?

Sim, você pode personalizar a aparência das formas ajustando suas propriedades como tamanho, posição, rotação e cor de preenchimento. Aspose.Words for Java oferece amplas opções para personalização de formas.

### O Aspose.Words para Java é compatível com SmartArt?

Sim, Aspose.Words for Java oferece suporte a formas SmartArt, permitindo que você trabalhe com diagramas e gráficos complexos em seus documentos.