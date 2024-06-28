---
title: Unindo e acrescentando documentos em Aspose.Words para Java
linktitle: Unindo e Anexando Documentos
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como juntar e anexar documentos sem esforço usando Aspose.Words for Java. Preserve a formatação, gerencie cabeçalhos, rodapés e muito mais.
type: docs
weight: 30
url: /pt/java/document-manipulation/joining-and-appending-documents/
---

## Introdução à junção e acréscimo de documentos em Aspose.Words for Java

Neste tutorial, exploraremos como juntar e anexar documentos usando a biblioteca Aspose.Words para Java. Você aprenderá como mesclar vários documentos sem problemas, preservando a formatação e a estrutura.

## Pré-requisitos

Antes de começar, certifique-se de ter a API Aspose.Words for Java configurada em seu projeto Java.

## Opções de junção de documentos

### Acrescentar Simples

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Anexar com opções de formato de importação

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Anexar ao documento em branco

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Anexar com conversões de número de página

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Converter campos NUMPAGES
dstDoc.updatePageLayout(); // Atualize o layout da página para numeração correta
```

## Lidando com diferentes configurações de página

Ao anexar documentos com configurações de página diferentes:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Certifique-se de que as configurações de página correspondam ao documento de destino
```

## Unindo documentos com estilos diferentes

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Comportamento de estilo inteligente

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Inserindo documentos com DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Mantendo a numeração da fonte

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Tratamento de caixas de texto

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Gerenciando cabeçalhos e rodapés

### Vinculando cabeçalhos e rodapés

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Desvinculando cabeçalhos e rodapés

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Conclusão

Aspose.Words for Java fornece ferramentas flexíveis e poderosas para juntar e anexar documentos, se você precisa manter a formatação, lidar com diferentes configurações de página ou gerenciar cabeçalhos e rodapés. Experimente essas técnicas para atender às suas necessidades específicas de processamento de documentos.

## Perguntas frequentes

### Como posso unir documentos com estilos diferentes de forma integrada?

 Para unir documentos com estilos diferentes, use`ImportFormatMode.USE_DESTINATION_STYLES` ao anexar.

### Posso preservar a numeração das páginas ao anexar documentos?

 Sim, você pode preservar a numeração das páginas usando o`convertNumPageFieldsToPageRef` método e atualizando o layout da página.

### O que é comportamento de estilo inteligente?

 O comportamento de estilo inteligente ajuda a manter estilos consistentes ao anexar documentos. Use-o com`ImportFormatOptions` para melhores resultados.

### Como posso lidar com caixas de texto ao anexar documentos?

Definir`importFormatOptions.setIgnoreTextBoxes(false)` para incluir caixas de texto durante o acréscimo.

### E se eu quiser vincular/desvincular cabeçalhos e rodapés entre documentos?

 Você pode vincular cabeçalhos e rodapés com`linkToPrevious(true)` ou desvinculá-los de`linkToPrevious(false)` como necessário.