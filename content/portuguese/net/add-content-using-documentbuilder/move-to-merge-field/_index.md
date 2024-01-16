---
title: Mover para mesclar campo em documento do Word
linktitle: Mover para mesclar campo em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como implementar o recurso Mover para mesclar campo no documento do Word do Aspose.Words for .NET usando o guia passo a passo.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/move-to-merge-field/
---
Neste exemplo, exploraremos o recurso Mover para mesclar campo no documento do Word do Aspose.Words for .NET. Aspose.Words é uma poderosa biblioteca de manipulação de documentos que permite aos desenvolvedores criar, modificar e converter documentos do Word programaticamente. O recurso Mover para mesclar campo nos permite navegar para mesclar campos em um documento e realizar várias operações neles.


## Explicando o código-fonte passo a passo

Vamos examinar o código-fonte passo a passo para entender como usar o recurso Move To Merge Field usando Aspose.Words for .NET.

## Etapa 1: inicializando o documento e o construtor de documentos

Primeiro, inicialize os objetos Document e DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passo 2 Inserindo um campo de mesclagem e adicionando texto depois dele

Use o método InsertField da classe DocumentBuilder para inserir um campo de mesclagem e adicione texto depois dele:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Etapa 3: O cursor do construtor está atualmente no final do documento.

```csharp
Assert.Null(builder.CurrentNode);
```
## Etapa 4: mover o cursor do construtor de documentos para o campo de mesclagem

Para mover o cursor do construtor de documentos para o campo de mesclagem, use o método MoveToField da classe DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Adicionando texto imediatamente após o campo de mesclagem

Assim que o cursor do construtor de documentos estiver dentro do campo de mesclagem, você poderá adicionar texto imediatamente após ele usando o método Write:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Exemplo de código-fonte para Move To Merge Field usando Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira um campo usando o DocumentBuilder e adicione uma sequência de texto depois dele.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// O cursor do construtor está atualmente no final do documento.
Assert.Null(builder.CurrentNode);
// Podemos mover o construtor para um campo como este, colocando o cursor imediatamente após o campo.
builder.MoveToField(field, true);

// Observe que o cursor está em um local além do nó FieldEnd do campo, o que significa que não estamos realmente dentro do campo.
// Se desejarmos mover o DocumentBuilder para dentro de um campo,
// precisaremos movê-lo para o nó FieldStart ou FieldSeparator de um campo usando o método DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusão

exploramos o recurso Move To Merge Field do Aspose.Words for .NET. Aprendemos como navegar para mesclar campos em um documento usando a classe DocumentBuilder e realizar operações neles. Este recurso é útil quando o processamento de palavras programaticamente com mesclagem

### Perguntas frequentes sobre como mover para mesclar campo em documento do Word

#### P: Qual é o propósito do recurso Mover para mesclar campo no Aspose.Words for .NET?

R: O recurso Mover para mesclar campo no Aspose.Words for .NET permite que os desenvolvedores naveguem para mesclar campos em um documento do Word e executem várias operações neles programaticamente. Os campos de mesclagem são espaços reservados especiais usados em documentos do Word para operações de mala direta.

#### P: Como posso inserir um campo de mesclagem em um documento do Word usando Aspose.Words for .NET?

R: Você pode usar o método InsertField da classe DocumentBuilder para inserir um campo de mesclagem no documento. Após inserir o campo de mesclagem, você pode adicionar conteúdo, como texto, antes ou depois do campo usando o método Write.

#### P: Como movo o cursor do construtor de documentos para um campo de mesclagem específico?

R: Para mover o cursor do construtor de documentos para um campo de mesclagem específico, use o método MoveToField da classe DocumentBuilder e passe o campo como parâmetro. Isto colocará o cursor imediatamente após o campo de mesclagem.

#### P: Posso adicionar texto dentro de um campo de mesclagem usando o recurso Mover para campo de mesclagem?

R: Não, o recurso Mover para mesclar campo coloca o cursor do construtor de documento imediatamente após o campo de mesclagem. Para adicionar texto dentro do campo de mesclagem, você pode usar o método DocumentBuilder.MoveTo para mover o cursor para o nó FieldStart ou FieldSeparator do campo de mesclagem.

#### P: Como posso realizar operações de mala direta usando Aspose.Words for .NET?

R: Aspose.Words for .NET fornece amplo suporte para operações de mala direta. Você pode usar a classe MailMerge para realizar mala direta usando dados de várias fontes, como matrizes, conjuntos de dados ou fontes de dados personalizadas.