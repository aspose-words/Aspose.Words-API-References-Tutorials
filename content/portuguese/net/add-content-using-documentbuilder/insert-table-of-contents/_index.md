---
title: Insira o índice no documento do Word
linktitle: Insira o índice no documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um índice em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Neste tutorial abrangente, você aprenderá como inserir um índice analítico em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você será capaz de gerar um índice com títulos e números de página apropriados.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: Crie um novo documento e DocumentBuilder
Para começar, crie um novo documento usando a classe Document e inicialize um objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir um índice
Em seguida, use o método InsertTableOfContents da classe DocumentBuilder para inserir um índice analítico. Especifique as opções de formatação necessárias no método:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Etapa 3: adicionar conteúdo do documento
Depois de inserir o índice, adicione o conteúdo real do documento. Defina os estilos de título apropriados usando StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Etapa 4: atualizar o índice
índice recém-inserido estará inicialmente vazio. Para preenchê-lo, atualize os campos do documento:

```csharp
doc.UpdateFields();
```

## Etapa 5: salve o documento
Após inserir o índice e atualizar os campos, salve o documento em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Exemplo de código-fonte para inserir índice usando Aspose.Words para .NET
Aqui está o código-fonte completo para inserir um índice usando Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicialize o DocumentBuilder com o objeto Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserir tabela de conteúdo
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Inicie o conteúdo real do documento na segunda página.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// O índice recém-inserido estará inicialmente vazio.
// Ele precisa ser preenchido atualizando os campos do documento.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Conclusão

Parabéns! Você aprendeu com sucesso como inserir um índice analítico em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e utilizando o código-fonte fornecido, agora você pode gerar um índice com títulos e números de página apropriados para seus documentos.

### Perguntas frequentes para inserir índice em documento do Word

#### P: Posso personalizar a aparência do índice?

 R: Sim, você pode personalizar a aparência do índice modificando as opções de formatação especificadas no`InsertTableOfContents` método. Os parâmetros permitem controlar os números das páginas, recuo e outros estilos.

#### P: E se eu quiser incluir níveis de títulos específicos no índice?

 R: Você pode especificar os níveis de títulos desejados a serem incluídos no índice ajustando o valor dentro do`InsertTableOfContents` método. Por exemplo, usando`"\\o \"1-3\""` incluirá os níveis de rubrica 1 a 3.

#### P: Posso atualizar o índice automaticamente se fizer alterações no conteúdo do documento?

 R: Sim, você pode atualizar o índice automaticamente chamando o`UpdateFields` método no documento. Isso garantirá que quaisquer alterações feitas no conteúdo do documento, como adicionar ou remover títulos, sejam refletidas no índice analítico.

#### P: Como posso definir um estilo diferente para os níveis de título no sumário?

 R: Você pode estilizar os níveis de título de maneira diferente usando diferentes estilos de parágrafo para cada nível de título. Ao atribuir diferentes`StyleIdentifier` valores para o`ParagraphFormat` do`DocumentBuilder`, você pode criar estilos distintos para cada nível de título.

#### P: É possível adicionar formatação adicional aos títulos do sumário?

 R: Sim, você pode adicionar formatação adicional aos títulos do índice, como estilos de fonte, cores ou outras propriedades. Ao ajustar o`Font` propriedades do`DocumentBuilder`, você pode aplicar formatação personalizada aos títulos.