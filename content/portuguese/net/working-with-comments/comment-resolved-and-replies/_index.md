---
title: Comentário resolvido e respostas
linktitle: Comentário resolvido e respostas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como resolver comentários e suas respostas em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-comments/comment-resolved-and-replies/
---

Neste tutorial abrangente, você aprenderá como resolver comentários e suas respostas em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você será capaz de gerenciar a resolução de comentários e atualizar o status dos comentários e suas respostas.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: carregar o documento e acessar os comentários
Para começar, carregue o documento que contém os comentários usando a classe Document e acesse a coleção de comentários:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Etapa 2: resolver comentários e suas respostas
Em seguida, percorra os comentários e suas respostas para marcá-los como resolvidos:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

No código acima, acessamos o comentário pai e iteramos por meio de suas respostas. Podemos recuperar o ID do comentário pai e seu status de resolução. Em seguida, atualizamos a marca “Concluído” de cada resposta de comentário para indicar a resolução.

## Etapa 3: salve o documento
Após resolver os comentários e atualizar seu status, salve o documento modificado em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Exemplo de código-fonte para resolver comentários e suas respostas usando Aspose.Words for .NET
Aqui está o código-fonte completo para resolver comentários e suas respostas usando Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Lembre-se de ajustar o código de acordo com seus requisitos específicos, incluindo o caminho do arquivo do documento e personalização adicional

## Conclusão
Parabéns! Você aprendeu com sucesso como resolver comentários e suas respostas em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode gerenciar a resolução de comentários e atualizar o status dos comentários e suas respostas de acordo com suas necessidades.

A resolução de comentários ajuda a rastrear e gerenciar feedback em um documento. Experimente diferentes status de comentários e personalize-os para melhorar os processos de colaboração e revisão em seus documentos.

### Perguntas frequentes

#### P: Como resolvo um comentário no Aspose.Words for .NET?

 R: Para resolver um comentário no Aspose.Words for .NET, você pode usar o`Comment.Resolve` método especificando o`Comment` objeto que você deseja resolver. Isso marcará o comentário como resolvido e o ocultará no documento final.

#### P: Como adiciono uma resposta a um comentário resolvido no Aspose.Words for .NET?

 R: Embora os comentários resolvidos estejam ocultos por padrão no documento final, você ainda pode adicionar uma resposta a um comentário resolvido usando o botão`Comment.AddReply`método especificando o texto da resposta e onde você deseja adicioná-lo.

#### P: Como posso ver os comentários resolvidos no Aspose.Words for .NET?

 R: Por padrão, os comentários resolvidos ficam ocultos no documento final. No entanto, você pode mostrá-los usando o`CommentOptions.ShowResolvedComments` propriedade do`Document` objeto e configurá-lo para`true`.

#### P: Como posso ocultar todos os comentários, incluindo respostas, no Aspose.Words for .NET?

 R: Para ocultar todos os comentários, incluindo respostas, no Aspose.Words for .NET, você pode usar o`CommentOptions.CommentDisplayMode` propriedade do`Document` objeto e configurá-lo para`CommentDisplayMode.None`.

#### P: Posso editar o texto de um comentário resolvido no Aspose.Words for .NET?

 R: Sim, você pode editar o texto de um comentário resolvido no Aspose.Words for .NET acessando o`Comment.Text` propriedade do correspondente`Comment` objeto e modificando o texto conforme necessário.