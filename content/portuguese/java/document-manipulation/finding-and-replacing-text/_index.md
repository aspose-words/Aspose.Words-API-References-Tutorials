---
title: Localizando e substituindo texto no Aspose.Words para Java
linktitle: Localizando e substituindo texto
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como encontrar e substituir texto em documentos do Word com o Aspose.Words para Java. Guia passo a passo com exemplos de código. Aprimore suas habilidades de manipulação de documentos Java.
type: docs
weight: 15
url: /pt/java/document-manipulation/finding-and-replacing-text/
---

## Introdução à localização e substituição de texto no Aspose.Words para Java

Aspose.Words para Java é uma API Java poderosa que permite que você trabalhe com documentos do Word programaticamente. Uma das tarefas comuns ao lidar com documentos do Word é encontrar e substituir texto. Se você precisa atualizar placeholders em modelos ou executar manipulações de texto mais complexas, o Aspose.Words para Java pode ajudar você a atingir seus objetivos de forma eficiente.

## Pré-requisitos

Antes de nos aprofundarmos nos detalhes de localização e substituição de texto, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de desenvolvimento Java
- Biblioteca Aspose.Words para Java
- Um documento Word de amostra para trabalhar

 Você pode baixar a biblioteca Aspose.Words para Java em[aqui](https://releases.aspose.com/words/java/).

## Localizando e substituindo texto simples

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie um DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Localizar e substituir texto
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salvar o documento modificado
doc.save("modified-document.docx");
```

 Neste exemplo, carregamos um documento do Word, criamos um`DocumentBuilder` , e use o`replace` método para localizar e substituir "texto antigo" por "texto novo" dentro do documento.

## Usando expressões regulares

Expressões regulares fornecem recursos poderosos de correspondência de padrões para pesquisa e substituição de texto. O Aspose.Words para Java oferece suporte a expressões regulares para operações de localização e substituição mais avançadas.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie um DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Use expressões regulares para localizar e substituir texto
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, usamos um padrão de expressão regular para localizar e substituir texto dentro do documento.

## Ignorando texto dentro de campos

Você pode configurar o Aspose.Words para ignorar o texto dentro dos campos ao executar operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina IgnoreFields como true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso é útil quando você deseja excluir texto dentro de campos, como campos de mesclagem, de serem substituídos.

## Ignorando texto dentro de revisões de exclusão

Você pode configurar o Aspose.Words para ignorar o texto dentro de revisões de exclusão durante operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina IgnoreDeleted como true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você exclua da substituição o texto que foi marcado para exclusão em alterações rastreadas.

## Ignorando texto dentro de revisões de inserção

Você pode configurar o Aspose.Words para ignorar o texto dentro das revisões de inserção durante as operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina IgnoreInserted como true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você exclua o texto que foi marcado como inserido nas alterações rastreadas de ser substituído.

## Substituindo texto por HTML

Você pode usar o Aspose.Words para Java para substituir texto por conteúdo HTML.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions com um retorno de chamada de substituição personalizado
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

 Neste exemplo, usamos um personalizado`ReplaceWithHtmlEvaluator` para substituir texto por conteúdo HTML.

## Substituindo texto em cabeçalhos e rodapés

Você pode localizar e substituir texto dentro de cabeçalhos e rodapés do seu documento do Word.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Obtenha a coleção de cabeçalhos e rodapés
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Escolha o tipo de cabeçalho ou rodapé no qual deseja substituir o texto (por exemplo, HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Crie uma instância FindReplaceOptions e aplique-a ao intervalo do rodapé
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você execute substituições de texto especificamente em cabeçalhos e rodapés.

## Exibindo alterações para ordens de cabeçalho e rodapé

Você pode usar o Aspose.Words para mostrar alterações nas ordens de cabeçalho e rodapé no seu documento.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Pegue a primeira seção
Section firstPageSection = doc.getFirstSection();

//Crie uma instância FindReplaceOptions e aplique-a ao intervalo do documento
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

// Substituir texto que afeta as ordens de cabeçalho e rodapé
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você visualize alterações relacionadas às ordens de cabeçalho e rodapé no seu documento.

## Substituindo texto por campos

Você pode substituir texto por campos usando Aspose.Words para Java.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina um retorno de chamada de substituição personalizado para campos
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Use opções ao substituir texto
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

 Neste exemplo, substituímos o texto por campos e especificamos o tipo de campo (por exemplo,`FieldType.FIELD_MERGE_FIELD`).

## Substituindo por um Avaliador

Você pode usar um avaliador personalizado para determinar o texto de substituição dinamicamente.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina um retorno de chamada de substituição personalizado
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Use opções ao substituir texto
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, usamos um avaliador personalizado (`MyReplaceEvaluator`) para substituir texto.

## Substituindo por Regex

O Aspose.Words para Java permite que você substitua texto usando expressões regulares.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Use expressões regulares para localizar e substituir texto
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, usamos um padrão de expressão regular para localizar e substituir texto dentro do documento.

## Reconhecimento e substituições dentro de padrões de substituição

Você pode reconhecer e fazer substituições dentro de padrões de substituição usando o Aspose.Words para Java.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions com UseSubstitutions definido como verdadeiro
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Use opções ao substituir texto por um padrão
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você execute substituições dentro dos padrões de substituição para substituições mais avançadas.

## Substituindo por uma String

Você pode substituir texto por uma string simples usando Aspose.Words para Java.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Substituir texto por uma string
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, substituímos "text-to-replace" por "new-string" dentro do documento.

## Usando a Ordem Legada

Você pode usar a ordem legada ao executar operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina UseLegacyOrder como true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Use opções ao substituir texto
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você use a ordem legada para operações de localização e substituição.

## Substituindo texto em uma tabela

Você pode localizar e substituir texto dentro de tabelas no seu documento do Word.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Obter uma tabela específica (por exemplo, a primeira tabela)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

//Use FindReplaceOptions para substituir texto na tabela
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salvar o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você execute substituições de texto especificamente dentro de tabelas.

## Conclusão

O Aspose.Words para Java fornece recursos abrangentes para encontrar e substituir texto em documentos do Word. Se você precisa executar substituições de texto simples ou operações mais avançadas usando expressões regulares, manipulações de campo ou avaliadores personalizados, o Aspose.Words para Java tem tudo o que você precisa. Certifique-se de explorar a extensa documentação e os exemplos fornecidos pelo Aspose para aproveitar todo o potencial desta poderosa biblioteca Java.

## Perguntas frequentes

### Como faço para baixar o Aspose.Words para Java?

 Você pode baixar o Aspose.Words para Java do site visitando[este link](https://releases.aspose.com/words/java/).

### Posso usar expressões regulares para substituição de texto?

Sim, você pode usar expressões regulares para substituição de texto no Aspose.Words para Java. Isso permite que você execute operações de localizar e substituir mais avançadas e flexíveis.

### Como posso ignorar o texto dentro dos campos durante a substituição?

Para ignorar o texto dentro dos campos durante a substituição, você pode definir o`IgnoreFields` propriedade do`FindReplaceOptions` para`true`. Isso garante que o texto dentro de campos, como campos de mesclagem, seja excluído da substituição.

### Posso substituir texto dentro de cabeçalhos e rodapés?

 Sim, você pode substituir texto dentro de cabeçalhos e rodapés do seu documento Word. Basta acessar o cabeçalho ou rodapé apropriado e usar o`replace` método com o desejado`FindReplaceOptions`.

### Para que serve a opção UseLegacyOrder?

O`UseLegacyOrder` opção em`FindReplaceOptions` permite que você use a ordem legada ao executar operações de localizar e substituir. Isso pode ser útil em certos cenários em que o comportamento da ordem legada é desejado.