---
title: Adicione comentários
linktitle: Adicione comentários
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar comentários a documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-comments/add-comments/
---

Neste tutorial abrangente, você aprenderá como adicionar comentários a um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá inserir comentários e personalizar seu conteúdo em seus documentos.

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

## Etapa 2: adicionar conteúdo ao documento
A seguir, adicione o conteúdo desejado ao documento usando o objeto DocumentBuilder. Neste exemplo, adicionamos algum texto:

```csharp
builder.Write("Some text is added.");
```

## Etapa 3: crie um comentário e adicione conteúdo
Para adicionar um comentário, crie uma instância da classe Comment, passando o objeto Document, o nome do autor, as iniciais do autor e a data atual:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Em seguida, anexe o comentário ao parágrafo atual:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Adicione conteúdo ao comentário, como um parágrafo e texto:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Etapa 4: salve o documento
Após adicionar o comentário e seu conteúdo, salve o documento em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Exemplo de código-fonte para adicionar comentários usando Aspose.Words for .NET
Aqui está o código-fonte completo para adicionar comentários usando Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como adicionar comentários a um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode inserir comentários e personalizar seu conteúdo em seus documentos.

Os comentários são úteis para colaboração, fornecendo informações adicionais ou fazendo anotações em um documento. Experimente diferentes nomes de autores, iniciais e conteúdos de comentários para atender às suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso adicionar um comentário em um documento Aspose.Words for .NET?

R: Para adicionar um comentário em um documento Aspose.Words for .NET, você precisa seguir as etapas mencionadas no tutorial.

#### P: Posso formatar o texto do comentário no Aspose.Words for .NET?

R: Sim, você pode formatar o texto do comentário no Aspose.Words for .NET usando as propriedades de formatação disponíveis.

#### P: Como posso recuperar todos os comentários presentes em um documento?

R: Você pode recuperar todos os comentários presentes em um documento usando o`Document.Comments` propriedade.

#### P: Posso excluir um comentário específico no Aspose.Words for .NET?

 R: Sim, você pode remover um comentário específico no Aspose.Words for .NET usando o`Comment.Remove` método.

#### P: Como posso modificar o texto de um comentário existente no Aspose.Words for .NET?

 R: Para modificar o texto de um comentário existente no Aspose.Words for .NET, você pode acessar o`Comment.Text` propriedade do correspondente`Comment` objeto e modifique o texto conforme necessário.