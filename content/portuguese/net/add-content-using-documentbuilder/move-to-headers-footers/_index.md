---
title: Mover para cabeçalhos e rodapés em documentos do Word
linktitle: Mover para cabeçalhos e rodapés em documentos do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar Aspose.Words for .NET para navegar e modificar cabeçalhos e rodapés em documentos do Word com este guia passo a passo.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/move-to-headers-footers/
---
Neste exemplo, exploraremos o recurso Mover para cabeçalhos e rodapés do Aspose.Words for .NET. Aspose.Words é uma poderosa biblioteca de manipulação de documentos que permite aos desenvolvedores criar, modificar e converter documentos do Word programaticamente. O recurso Mover para cabeçalhos/rodapés nos permite navegar para diferentes cabeçalhos e rodapés em um documento e adicionar conteúdo a eles.

Vamos examinar o código-fonte passo a passo para entender como usar o recurso Mover para cabeçalhos/rodapés usando Aspose.Words for .NET.

## Etapa 1: inicializando o documento e o construtor de documentos

Primeiro, inicialize os objetos Document e DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: configurar cabeçalhos e rodapés

Especifique as configurações de cabeçalho/rodapé do documento. Neste exemplo, definimos os cabeçalhos e rodapés como diferentes para a primeira página e para páginas pares/ímpares:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Etapa 3: Criação de cabeçalhos para páginas diferentes

Vá para cada tipo de cabeçalho e adicione conteúdo a eles. Neste exemplo, criamos cabeçalhos para a primeira página, páginas pares e todas as outras páginas:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Passo 4: Criando páginas no documento
Adicione conteúdo ao documento para criar várias páginas. Por exemplo:

```csharp
// Crie duas páginas no documento.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Passo 5: Salvando o documento

Salve o documento modificado no local desejado:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Certifique-se de especificar o caminho e formato de arquivo apropriado (por exemplo, DOCX).

### Exemplo de código-fonte para mover para cabeçalhos/rodapés usando Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Especifique que queremos cabeçalhos e rodapés diferentes para páginas primeiras, pares e ímpares.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Crie os cabeçalhos.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Crie duas páginas no documento.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## Conclusão

Neste exemplo, exploramos o recurso Mover para cabeçalhos/rodapés do Aspose.Words for .NET. Aprendemos como navegar por diferentes cabeçalhos e rodapés em um documento do Word e adicionar conteúdo a eles usando a classe DocumentBuilder. Esse recurso permite que os desenvolvedores personalizem cabeçalhos e rodapés para páginas ou seções específicas, proporcionando flexibilidade na criação de documentos profissionais e estruturados. Aspose.Words for .NET fornece um poderoso conjunto de ferramentas para manipulação programática de documentos do Word, tornando-o uma biblioteca essencial para aplicativos de processamento de documentos.

### Perguntas frequentes sobre como mover para cabeçalhos e rodapés em documentos do Word

#### P: Qual é o propósito do recurso Mover para cabeçalhos/rodapés no Aspose.Words for .NET?

R: O recurso Mover para cabeçalhos/rodapés no Aspose.Words for .NET permite que os desenvolvedores naveguem para diferentes cabeçalhos e rodapés em um documento do Word e adicionem conteúdo a eles programaticamente. É útil quando você precisa personalizar cabeçalhos e rodapés para diferentes páginas ou seções do documento.

#### P: Posso ter cabeçalhos e rodapés diferentes para páginas diferentes do documento?

R: Sim, você pode especificar diferentes cabeçalhos e rodapés para a primeira página, páginas pares e páginas ímpares usando as propriedades PageSetup.DifferentFirstPageHeaderFooter e PageSetup.OddAndEvenPagesHeaderFooter, respectivamente.

#### P: Como posso adicionar conteúdo a cabeçalhos e rodapés específicos?

R: Para adicionar conteúdo a cabeçalhos e rodapés específicos, use o método MoveToHeaderFooter da classe DocumentBuilder. Você pode passar para os cabeçalhos HeaderFirst, HeaderEven e HeaderPrimary ou para os rodapés FooterFirst, FooterEven e FooterPrimary com base em sua necessidade.

#### P: Posso criar cabeçalhos e rodapés para uma seção específica do documento?

R: Sim, você pode usar o método MoveToSection da classe DocumentBuilder para mover para uma seção específica do documento e então criar cabeçalhos e rodapés dentro dessa seção.

#### P: Como posso salvar o documento modificado em um arquivo usando Aspose.Words for .NET?

R: Você pode salvar o documento modificado em um local e formato desejados usando o método Save da classe Document. Certifique-se de especificar o caminho e o formato de arquivo apropriados (por exemplo, DOCX).