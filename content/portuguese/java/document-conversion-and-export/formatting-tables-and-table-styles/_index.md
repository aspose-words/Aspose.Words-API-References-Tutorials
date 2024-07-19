---
title: Formatando tabelas e estilos de tabela em Aspose.Words para Java
linktitle: Formatando Tabelas e Estilos de Tabela
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como formatar tabelas e aplicar estilos de tabela em Aspose.Words for Java. Explore guias passo a passo com código-fonte para uma formatação de tabela eficaz. Aprimore o layout do seu documento com Aspose.Words.
type: docs
weight: 17
url: /pt/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Introdução à formatação de tabelas e estilos de tabela em Aspose.Words for Java

As tabelas desempenham um papel crucial na estruturação e organização das informações nos documentos. Aspose.Words for Java fornece recursos poderosos para formatar tabelas e aplicar estilos de tabela para aprimorar o apelo visual de seus documentos. Neste guia passo a passo, exploraremos vários aspectos da formatação de tabelas e da aplicação de estilos de tabela usando Aspose.Words for Java.

## Pré-requisitos

Antes de entrarmos nos detalhes, certifique-se de ter a biblioteca Aspose.Words for Java integrada ao seu projeto. Você pode baixá-lo no site da Aspose:[Baixe Aspose.Words para Java](https://releases.aspose.com/words/java/).

## Obtenha distância entre a tabela e o texto circundante

Para começar, vamos explorar como recuperar a distância entre uma tabela e o texto ao redor em um documento.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Aplicar borda de contorno a uma tabela

Você pode alinhar uma tabela ao centro da página, limpar as bordas existentes e definir uma borda de contorno personalizada com este código:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## Construa uma mesa com bordas

Este trecho de código demonstra como criar uma tabela e definir bordas para a tabela e suas células:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Modificar formatação de linha

Aprenda como modificar a formatação de uma linha específica em uma tabela:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Aplicar formatação de linha

Este exemplo demonstra como aplicar formatação a uma linha inteira de uma tabela:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Definir preenchimento de célula

Explore como definir o preenchimento para células individuais em uma tabela:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Modificar formatação de célula

Descubra como modificar a formatação de uma célula específica dentro de uma tabela:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formatar tabela e célula com bordas diferentes

Aprenda como definir bordas diferentes para células individuais em uma tabela:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Defina as bordas da mesa
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Definir sombreamento de células para células individuais
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Adicione conteúdo às células
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Limpar formatação de célula para a próxima linha
builder.getCellFormat().clearFormatting();
// Crie bordas maiores para a primeira célula desta linha
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Definir título e descrição da tabela

Adicione um título e uma descrição à sua tabela:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Etapa 10: permitir espaçamento entre células

Permita o espaçamento entre células e defina seu valor para uma tabela:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Passo 11: Construa uma Mesa com Estilo

Crie uma tabela com um estilo predefinido:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Etapa 12: Expanda a formatação em células e linhas do estilo

Aprenda como expandir estilos de tabela para aplicar formatação a células e linhas:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Etapa 13: Crie um estilo de tabela

Crie um estilo de tabela personalizado com formatação específica:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Etapa 14: Definir formatação condicional

Aplique formatação condicional às linhas de uma tabela:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Etapa 15: definir a formatação do TableCell

Defina uma formatação específica para células individuais:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Etapa 16: definir a formatação do TableRow

Aplique formatação a linhas inteiras de uma tabela:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Conclusão

Aspose.Words for Java permite formatar tabelas e aplicar estilos de tabela com precisão. Desde a modificação da formatação de células individuais até a criação de estilos de tabela personalizados, você tem as ferramentas para tornar seus documentos visualmente atraentes e organizados.

## Perguntas frequentes

### Como faço o download do Aspose.Words para Java?

 Você pode baixar Aspose.Words para Java no site da Aspose:[Baixe Aspose.Words para Java](https://releases.aspose.com/words/java/).

### Posso aplicar bordas diferentes a células individuais de uma tabela?

Sim, você pode definir bordas diferentes para células individuais em uma tabela usando Aspose.Words for Java, conforme demonstrado neste guia.

### Qual é o propósito de definir um título e uma descrição de tabela?

Definir um título e uma descrição de tabela melhora a acessibilidade e a organização do seu documento, facilitando a compreensão do conteúdo pelos leitores e pelas tecnologias assistenciais.

### Como posso aplicar formatação condicional a linhas específicas de uma tabela?

Você pode aplicar formatação condicional a linhas específicas de uma tabela definindo estilos de tabela personalizados com regras de formatação condicional, conforme mostrado neste guia.

### Onde posso encontrar mais documentação e recursos para Aspose.Words for Java?

 Para obter documentação abrangente e recursos adicionais, visite a documentação do Aspose.Words para Java:[Documentação Aspose.Words para Java](https://reference.aspose.com/words/java/).