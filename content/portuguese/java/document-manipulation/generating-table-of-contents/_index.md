---
title: Gerando índice em Aspose.Words para Java
linktitle: Gerando Índice
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como gerar e personalizar o Índice (TOC) usando Aspose.Words para Java. Crie documentos organizados e profissionais sem esforço.
type: docs
weight: 21
url: /pt/java/document-manipulation/generating-table-of-contents/
---

## Introdução à geração de índice em Aspose.Words para Java

Neste tutorial, orientaremos você no processo de geração de um Índice (TOC) usando Aspose.Words para Java. TOC é um recurso crucial para a criação de documentos organizados. Abordaremos como personalizar a aparência e o layout do sumário.

## Pré-requisitos

Antes de começar, certifique-se de ter o Aspose.Words for Java instalado e configurado em seu projeto Java.

## Etapa 1: crie um novo documento

Primeiro, vamos criar um novo documento para trabalhar.

```java
Document doc = new Document();
```

## Etapa 2: personalizar estilos de sumário

Para personalizar a aparência do seu sumário, você pode modificar os estilos associados a ele. Neste exemplo, deixaremos as entradas do sumário de primeiro nível em negrito.

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## Etapa 3: adicione conteúdo ao seu documento

Você pode adicionar seu conteúdo ao documento. Este conteúdo será utilizado para gerar o TOC.

## Etapa 4: gerar o sumário

Para gerar o TOC, insira um campo TOC no local desejado do seu documento. Este campo será preenchido automaticamente com base nos títulos e estilos do seu documento.

```java
// Insira um campo de sumário no local desejado em seu documento.
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## Etapa 5: salve o documento

Por fim, salve o documento com o sumário.

```java
doc.save("your_output_path_here");
```

## Personalizando paradas de tabulação no sumário

Você também pode personalizar as paradas de tabulação em seu sumário para controlar o layout dos números das páginas. Veja como você pode alterar as paradas de tabulação:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //Obtenha a primeira guia usada neste parágrafo, que alinha os números das páginas.
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // Remova a guia antiga.
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // Insira uma nova aba em uma posição modificada (por exemplo, 50 unidades à esquerda).
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

Agora você tem um índice personalizado em seu documento com paradas de tabulação ajustadas para alinhamento do número de página.


## Conclusão

Neste tutorial, exploramos como gerar um Índice (TOC) usando Aspose.Words for Java, uma biblioteca poderosa para trabalhar com documentos do Word. Um sumário bem estruturado é essencial para organizar e navegar em documentos extensos, e o Aspose.Words fornece as ferramentas para criar e personalizar sumários sem esforço.

## Perguntas frequentes

### Como altero a formatação das entradas do sumário?

 Você pode modificar os estilos associados aos níveis do sumário usando`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`, onde X é o nível de TOC.

### Como posso adicionar mais níveis ao meu sumário?

Para incluir mais níveis em seu sumário, você pode modificar o campo sumário e especificar o número desejado de níveis.

### Posso alterar as posições das paradas de tabulação para entradas específicas do sumário?

Sim, conforme mostrado no exemplo de código acima, você pode alterar as posições das paradas de tabulação para entradas específicas do sumário iterando pelos parágrafos e modificando as paradas de tabulação de acordo.