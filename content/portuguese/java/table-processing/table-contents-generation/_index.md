---
title: Índice Geração
linktitle: Índice Geração
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda a criar Índice dinâmico usando Aspose.Words para Java. Domine a geração de TOC com orientação passo a passo e exemplos de código-fonte.
type: docs
weight: 14
url: /pt/java/table-processing/table-contents-generation/
---
## Introdução

Já teve dificuldades para criar um Índice (TOC) dinâmico e com aparência profissional em seus documentos do Word? Não procure mais! Com o Aspose.Words para Java, você pode automatizar todo o processo, economizando tempo e garantindo precisão. Não importa se você está criando um relatório abrangente ou um artigo acadêmico, este tutorial o guiará pela geração de um TOC programaticamente com Java. Pronto para mergulhar? Vamos começar!

## Pré-requisitos

Antes de começar a codificar, certifique-se de ter o seguinte:

1.  Java Development Kit (JDK): Instalado no seu sistema. Você pode baixá-lo em[Site da Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Biblioteca Aspose.Words para Java: Baixe a versão mais recente do[página de lançamento](https://releases.aspose.com/words/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): como IntelliJ IDEA, Eclipse ou NetBeans.
4.  Licença temporária Aspose: para evitar limitações de avaliação, obtenha uma[licença temporária](https://purchase.aspose.com/temporary-license/).

## Pacotes de importação

Para usar o Aspose.Words para Java efetivamente, certifique-se de importar as classes necessárias. Aqui estão as importações:

```java
import com.aspose.words.*;
```

Siga estas etapas para gerar um índice dinâmico no seu documento do Word.

## Etapa 1: inicializar o documento e o DocumentBuilder

 O primeiro passo é criar um novo documento e usar o`DocumentBuilder` classe para manipulá-lo.


```java
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

- `Document`: Representa o documento do Word.
- `DocumentBuilder`: Uma classe auxiliar que permite fácil manipulação do documento.

## Etapa 2: Insira o Índice

Agora, vamos inserir o TOC no início do documento.


```java
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");
builder.insertBreak(BreakType.PAGE_BREAK);
```

- `insertTableOfContents`: Insere um campo TOC. Os parâmetros especificam:
  - `\o "1-3"`: Incluir títulos dos níveis 1 a 3.
  - `\h`: Transforme entradas em hiperlinks.
  - `\z`: Suprimir números de página para documentos da web.
  - `\u`: Preservar estilos para hiperlinks.
- `insertBreak`: Adiciona uma quebra de página após o TOC.

## Etapa 3: adicione títulos para preencher o TOC

Para preencher o índice, você precisa adicionar parágrafos com estilos de título.


```java
builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);
builder.writeln("Heading 1");

builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_2);
builder.writeln("Heading 1.1");
builder.writeln("Heading 1.2");

builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);
builder.writeln("Heading 2");
```

- `setStyleIdentifier` : Define o estilo do parágrafo para um nível de título específico (por exemplo,`HEADING_1`, `HEADING_2`).
- `writeln`: Adiciona texto ao documento com o estilo especificado.

## Etapa 4: Adicionar títulos aninhados

Para demonstrar os níveis do TOC, inclua títulos aninhados.


```java
builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_3);
builder.writeln("Heading 3.1.1");
builder.writeln("Heading 3.1.2");
builder.writeln("Heading 3.1.3");

builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_4);
builder.writeln("Heading 3.1.3.1");
builder.writeln("Heading 3.1.3.2");
```

- Adicione títulos de níveis mais profundos para mostrar a hierarquia no índice.

## Etapa 5: Atualizar campos do TOC

O campo TOC deve ser atualizado para exibir os títulos mais recentes.


```java
doc.updateFields();
```

- `updateFields`: Atualiza todos os campos no documento, garantindo que o TOC reflita os títulos adicionados.

## Etapa 6: Salve o documento

Por fim, salve o documento no formato desejado.


```java
doc.save(dataDir + "DocumentBuilder.InsertToc.docx");
```

- `save` : Exporta o documento para um`.docx` arquivo. Você pode especificar outros formatos, como`.pdf` ou`.txt` se necessário.

## Conclusão

Parabéns! Você criou com sucesso um Índice dinâmico em um documento do Word usando o Aspose.Words para Java. Com apenas algumas linhas de código, você automatizou uma tarefa que poderia levar horas. Então, o que vem a seguir? Tente experimentar diferentes estilos e formatos de título para adaptar seu TOC a necessidades específicas.

## Perguntas frequentes

### Posso personalizar ainda mais o formato do TOC?
Claro! Você pode ajustar parâmetros do TOC, como incluir números de página, alinhar texto ou usar estilos de título personalizados.

### É obrigatória uma licença para o Aspose.Words para Java?
 Sim, uma licença é necessária para a funcionalidade completa. Você pode começar com uma[licença temporária](https://purchase.aspose.com/temporary-license/).

### Posso gerar um índice para um documento existente?
 Sim! Carregue o documento em um`Document` objeto e siga os mesmos passos para inserir e atualizar o TOC.

### Isso funciona para exportações de PDF?
 Sim, o TOC aparecerá no PDF se você salvar o documento em`.pdf` formatar.

### Onde posso encontrar mais documentação?
 Confira o[Aspose.Words para documentação Java](https://reference.aspose.com/words/java/) para mais exemplos e detalhes.