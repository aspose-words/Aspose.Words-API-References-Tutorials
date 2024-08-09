---
title: Adicionando conteúdo usando DocumentBuilder em Aspose.Words for Java
linktitle: Adicionando conteúdo usando DocumentBuilder
second_title: API de processamento de documentos Java Aspose.Words
description: Domine a criação de documentos com Aspose.Words para Java. Um guia passo a passo para adicionar texto, tabelas, imagens e muito mais. Crie documentos impressionantes do Word sem esforço.
type: docs
weight: 26
url: /pt/java/document-manipulation/adding-content-using-documentbuilder/
---

## Introdução à adição de conteúdo usando DocumentBuilder em Aspose.Words for Java

Neste guia passo a passo, exploraremos como usar o Aspose.Words for Java's DocumentBuilder para adicionar vários tipos de conteúdo a um documento do Word. Abordaremos a inserção de texto, tabelas, regras horizontais, campos de formulário, HTML, hiperlinks, sumário, imagens embutidas e flutuantes, parágrafos e muito mais. Vamos começar!

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Words for Java configurada em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/java/).

## Adicionando Texto

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira um parágrafo de texto simples
builder.write("This is a simple text paragraph.");

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando tabelas

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Comece uma mesa
Table table = builder.startTable();

// Inserir células e conteúdo
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// Acabar com a mesa
builder.endTable();

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando regra horizontal

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserir uma régua horizontal
builder.insertHorizontalRule();

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando campos de formulário

### Campo de formulário de entrada de texto

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira um campo de formulário de entrada de texto
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Salve o documento
doc.save("path/to/your/document.docx");
```

### Campo de formulário de caixa de seleção

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira um campo de formulário com caixa de seleção
builder.insertCheckBox("CheckBox", true, true, 0);

// Salve o documento
doc.save("path/to/your/document.docx");
```

### Campo de formulário de caixa de combinação

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definir itens para a caixa de combinação
String[] items = { "Option 1", "Option 2", "Option 3" };

// Insira um campo de formulário de caixa de combinação
builder.insertComboBox("DropDown", items, 0);

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando HTML

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserir conteúdo HTML
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando hiperlinks

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira um hiperlink
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", falso);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando um índice

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira um índice
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Adicionar conteúdo do documento
// ...

// Atualizar o índice
doc.updateFields();

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando imagens

### Imagem embutida

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira uma imagem embutida
builder.insertImage("path/to/your/image.png");

// Salve o documento
doc.save("path/to/your/document.docx");
```

### Imagem flutuante

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira uma imagem flutuante
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Adicionando parágrafos

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definir formatação de parágrafo
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Insira um parágrafo
builder.writeln("This is a formatted paragraph.");

// Salve o documento
doc.save("path/to/your/document.docx");
```

## Etapa 10: Movendo o Cursor

 Você pode controlar a posição do cursor no documento usando vários métodos como`moveToParagraph`, `moveToCell`muito mais. Aqui está um exemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mova o cursor para um parágrafo específico
builder.moveToParagraph(2, 0);

// Adicione conteúdo na nova posição do cursor
builder.writeln("This is the 3rd paragraph.");
```

Estas são algumas operações comuns que você pode realizar usando Aspose.Words for Java's DocumentBuilder. Explore a documentação da biblioteca para recursos mais avançados e opções de personalização. Feliz criação de documentos!


## Conclusão

Neste guia abrangente, exploramos os recursos do Aspose.Words for Java's DocumentBuilder para adicionar vários tipos de conteúdo a documentos do Word. Abordamos texto, tabelas, regras horizontais, campos de formulário, HTML, hiperlinks, índice analítico, imagens, parágrafos e movimento do cursor.

## Perguntas frequentes

### P: O que é Aspose.Words para Java?

R: Aspose.Words for Java é uma biblioteca Java que permite aos desenvolvedores criar, modificar e manipular documentos do Microsoft Word programaticamente. Ele fornece uma ampla gama de recursos para geração, formatação e inserção de conteúdo de documentos.

### P: Como posso adicionar um índice ao meu documento?

R: Para adicionar um índice, use o`DocumentBuilder` para inserir um campo de índice em seu documento. Certifique-se de atualizar os campos no documento após adicionar conteúdo para preencher o índice. Aqui está um exemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira um campo de índice
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Adicionar conteúdo do documento
// ...

// Atualizar o índice
doc.updateFields();
```

### P: Como insiro imagens em um documento usando Aspose.Words for Java?

 R: Você pode inserir imagens, tanto inline quanto flutuantes, usando o`DocumentBuilder`. Aqui estão exemplos de ambos:

#### Imagem embutida:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira uma imagem embutida
builder.insertImage("path/to/your/image.png");
```

#### Imagem flutuante:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira uma imagem flutuante
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### P: Posso formatar texto e parágrafos ao adicionar conteúdo?

 R: Sim, você pode formatar texto e parágrafos usando o`DocumentBuilder`. Você pode definir propriedades de fonte, alinhamento de parágrafo, recuo e muito mais. Aqui está um exemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definir formatação de fonte e parágrafo
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Inserir um parágrafo formatado
builder.writeln("This is a formatted paragraph.");
```

### P: Como posso mover o cursor para um local específico no documento?

 R: Você pode controlar a posição do cursor usando métodos como`moveToParagraph`, `moveToCell`muito mais. Aqui está um exemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mova o cursor para um parágrafo específico
builder.moveToParagraph(2, 0);

// Adicione conteúdo na nova posição do cursor
builder.writeln("This is the 3rd paragraph.");
```

Estas são algumas perguntas e respostas comuns para ajudá-lo a começar a usar o Aspose.Words for Java's DocumentBuilder. Se você tiver mais dúvidas ou precisar de mais assistência, consulte o[documentação da biblioteca](https://reference.aspose.com/words/java/) ou procure ajuda da comunidade Aspose.Words e recursos de suporte.