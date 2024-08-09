---
title: Localizando e substituindo texto em Aspose.Words para Java
linktitle: Encontrar e substituir texto
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como localizar e substituir texto em documentos do Word com Aspose.Words for Java. Guia passo a passo com exemplos de código. Aprimore suas habilidades de manipulação de documentos Java.
type: docs
weight: 15
url: /pt/java/document-manipulation/finding-and-replacing-text/
---

## Introdução à localização e substituição de texto em Aspose.Words for Java

Aspose.Words for Java é uma API Java poderosa que permite trabalhar com documentos do Word programaticamente. Uma das tarefas comuns ao lidar com documentos do Word é localizar e substituir texto. Se você precisa atualizar espaços reservados em modelos ou realizar manipulações de texto mais complexas, o Aspose.Words for Java pode ajudá-lo a atingir seus objetivos com eficiência.

## Pré-requisitos

Antes de nos aprofundarmos nos detalhes de localização e substituição de texto, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de Desenvolvimento Java
- Biblioteca Aspose.Words para Java
- Um exemplo de documento do Word para trabalhar

 Você pode baixar a biblioteca Aspose.Words para Java em[aqui](https://releases.aspose.com/words/java/).

## Encontrar e substituir texto simples

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie um DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Localizar e substituir texto
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salve o documento modificado
doc.save("modified-document.docx");
```

 Neste exemplo, carregamos um documento Word, criamos um`DocumentBuilder` e use o`replace` método para localizar e substituir "texto antigo" por "texto novo" no documento.

## Usando expressões regulares

As expressões regulares fornecem recursos poderosos de correspondência de padrões para pesquisa e substituição de texto. Aspose.Words for Java oferece suporte a expressões regulares para operações mais avançadas de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie um DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Use expressões regulares para localizar e substituir texto
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Salve o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, usamos um padrão de expressão regular para localizar e substituir texto no documento.

## Ignorando texto dentro dos campos

Você pode configurar Aspose.Words para ignorar o texto dentro dos campos ao executar operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina IgnoreFields como true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso é útil quando você deseja excluir a substituição de texto dentro de campos, como campos de mesclagem.

## Ignorando texto dentro de deletar revisões

Você pode configurar Aspose.Words para ignorar o texto dentro das revisões de exclusão durante as operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina IgnoreDeleted como true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você exclua a substituição do texto que foi marcado para exclusão nas alterações controladas.

## Ignorando o texto dentro das revisões de inserção

Você pode configurar Aspose.Words para ignorar o texto dentro das revisões de inserção durante as operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina IgnoreInserted como true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você exclua a substituição do texto marcado como inserido nas alterações controladas.

## Substituindo Texto por HTML

Você pode usar Aspose.Words for Java para substituir texto por conteúdo HTML.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions com um retorno de chamada de substituição personalizado
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Use opções ao substituir texto
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

 Neste exemplo, usamos um costume`ReplaceWithHtmlEvaluator` para substituir texto por conteúdo HTML.

## Substituindo texto em cabeçalhos e rodapés

Você pode localizar e substituir texto nos cabeçalhos e rodapés do seu documento do Word.

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

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso permite realizar substituições de texto especificamente em cabeçalhos e rodapés.

## Mostrando alterações em pedidos de cabeçalho e rodapé

Você pode usar Aspose.Words para mostrar alterações nas ordens de cabeçalho e rodapé em seu documento.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Obtenha a primeira seção
Section firstPageSection = doc.getFirstSection();

// Crie uma instância FindReplaceOptions e aplique-a ao intervalo do documento
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Substitua o texto que afeta as ordens de cabeçalho e rodapé
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso permite visualizar alterações relacionadas às ordens de cabeçalho e rodapé em seu documento.

## Substituindo Texto por Campos

Você pode substituir texto por campos usando Aspose.Words for Java.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina um retorno de chamada de substituição personalizado para campos
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Use opções ao substituir texto
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

 Neste exemplo, substituímos texto por campos e especificamos o tipo de campo (por exemplo,`FieldType.FIELD_MERGE_FIELD`).

## Substituindo por um Avaliador

Você pode usar um avaliador customizado para determinar o texto de substituição dinamicamente.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina um retorno de chamada de substituição personalizado
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Use opções ao substituir texto
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, usamos um avaliador personalizado (`MyReplaceEvaluator`) para substituir o texto.

## Substituindo por Regex

Aspose.Words for Java permite substituir texto usando expressões regulares.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Use expressões regulares para localizar e substituir texto
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Salve o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, usamos um padrão de expressão regular para localizar e substituir texto no documento.

## Reconhecimento e substituições dentro de padrões de substituição

Você pode reconhecer e fazer substituições em padrões de substituição usando Aspose.Words for Java.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

//Crie uma instância FindReplaceOptions com UseSubstitutions definido como verdadeiro
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Use opções ao substituir texto por um padrão
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso permite realizar substituições dentro dos padrões de substituição para substituições mais avançadas.

## Substituindo por uma String

Você pode substituir o texto por uma string simples usando Aspose.Words for Java.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Substitua o texto por uma string
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Salve o documento modificado
doc.save("modified-document.docx");
```

Neste exemplo, substituímos “text-to-replace” por “new-string” no documento.

## Usando pedido herdado

Você pode usar a ordem herdada ao executar operações de localização e substituição.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Crie uma instância FindReplaceOptions e defina UseLegacyOrder como true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Use opções ao substituir texto
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso permite que você use a ordem herdada para operações de localização e substituição.

## Substituindo Texto em uma Tabela

Você pode localizar e substituir texto em tabelas em seu documento do Word.

```java
// Carregue o documento
Document doc = new Document("your-document.docx");

// Obtenha uma tabela específica (por exemplo, a primeira tabela)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Use FindReplaceOptions para substituir texto na tabela
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salve o documento modificado
doc.save("modified-document.docx");
```

Isso permite realizar substituições de texto especificamente em tabelas.

## Conclusão

Aspose.Words for Java fornece recursos abrangentes para localizar e substituir texto em documentos do Word. Se você precisa realizar substituições de texto simples ou operações mais avançadas usando expressões regulares, manipulações de campo ou avaliadores personalizados, Aspose.Words for Java tem o que você precisa. Certifique-se de explorar a extensa documentação e exemplos fornecidos por Aspose para aproveitar todo o potencial desta poderosa biblioteca Java.

## Perguntas frequentes

### Como faço o download do Aspose.Words para Java?

 Você pode baixar Aspose.Words for Java do site visitando[este link](https://releases.aspose.com/words/java/).

### Posso usar expressões regulares para substituição de texto?

Sim, você pode usar expressões regulares para substituição de texto em Aspose.Words for Java. Isso permite que você execute operações de localização e substituição mais avançadas e flexíveis.

### Como posso ignorar o texto dentro dos campos durante a substituição?

 Para ignorar o texto dentro dos campos durante a substituição, você pode definir o`IgnoreFields` propriedade do`FindReplaceOptions` para`true`Isso garante que o texto dentro dos campos, como campos de mesclagem, seja excluído da substituição.

### Posso substituir o texto dentro dos cabeçalhos e rodapés?

 Sim, você pode substituir o texto nos cabeçalhos e rodapés do seu documento do Word. Basta acessar o cabeçalho ou rodapé apropriado e usar o`replace` método com o desejado`FindReplaceOptions`.

### Para que serve a opção UseLegacyOrder?

 O`UseLegacyOrder` opção em`FindReplaceOptions` permite que você use a ordem herdada ao executar operações de localização e substituição. Isso pode ser útil em determinados cenários onde o comportamento do pedido herdado é desejado.