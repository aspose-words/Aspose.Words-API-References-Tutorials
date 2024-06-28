---
title: Adicionar Remover Resposta de Comentário
linktitle: Adicionar Remover Resposta de Comentário
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar e remover respostas de comentários em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-comments/add-remove-comment-reply/
---

Neste tutorial abrangente, você aprenderá como adicionar e remover respostas de comentários em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá gerenciar as respostas aos comentários e personalizá-las de acordo com suas necessidades.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: carregue o documento
Para começar, carregue o documento que contém os comentários usando a classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Etapa 2: acesse o comentário e gerencie as respostas
A seguir, acesse o comentário do documento usando o método GetChild com o parâmetro NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Para remover uma resposta do comentário, use o método RemoveReply e forneça o índice de resposta desejado:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Para adicionar uma nova resposta ao comentário, use o método AddReply e forneça o nome do autor, as iniciais do autor, a data e hora e o texto da resposta:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Etapa 3: salve o documento
Após adicionar ou remover respostas de comentários, salve o documento em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Exemplo de código-fonte para adicionar e remover respostas de comentários usando Aspose.Words for .NET
Aqui está o código-fonte completo para adicionar e remover respostas de comentários usando Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como adicionar e remover respostas de comentários em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode gerenciar respostas de comentários e personalizá-las de acordo com suas necessidades.

As respostas aos comentários permitem discussões colaborativas e feedback dentro de um documento. Experimente diferentes autores de respostas, iniciais, datas e textos para aprimorar a colaboração e a comunicação em seus documentos.

### Perguntas frequentes

#### P: Como posso adicionar um comentário no Aspose.Words for .NET?

 R: Para adicionar um comentário no Aspose.Words for .NET, você pode usar o`Comment.AddComment` método especificando o texto do comentário e onde você deseja adicioná-lo no documento.

#### P: Como posso remover um comentário no Aspose.Words for .NET?

R: Para remover um comentário no Aspose.Words for .NET, você pode usar o`Comment.Remove` método especificando o`Comment` objeto que você deseja remover.

#### P: Posso responder a um comentário no Aspose.Words for .NET?

 R: Sim, você pode responder a um comentário no Aspose.Words for .NET usando o`Comment.AddReply` método especificando o texto da resposta e onde você deseja adicioná-lo no documento.

#### P: Como posso acessar comentários existentes no Aspose.Words for .NET?

 R: Você pode acessar comentários existentes no Aspose.Words for .NET usando o`CommentCollection` propriedade do`Document` objeto. Isso permitirá que você navegue por todos os comentários presentes no documento.

#### P: Posso editar o texto do comentário no Aspose.Words for .NET?

 R: Sim, você pode editar o texto de um comentário no Aspose.Words for .NET acessando o`Comment.Text` propriedade do correspondente`Comment` objeto e modificando o texto conforme necessário.