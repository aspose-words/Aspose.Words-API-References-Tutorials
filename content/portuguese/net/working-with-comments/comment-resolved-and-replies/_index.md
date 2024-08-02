---
title: Comentário resolvido e respostas
linktitle: Comentário resolvido e respostas
second_title: API de processamento de documentos Aspose.Words
description: Automatize a resolução e resposta a comentários em documentos do Word com Aspose.Words for .NET. Guia passo a passo incluído.
type: docs
weight: 10
url: /pt/net/working-with-comments/comment-resolved-and-replies/
---
## Introdução

Se você estiver trabalhando com documentos do Word, provavelmente já lidou com comentários. Eles são ótimos para colaboração, mas gerenciá-los pode ser um incômodo. Com Aspose.Words for .NET, você pode automatizar o processo de resolução e resposta a comentários. Este guia orientará você nas etapas para fazer exatamente isso.

## Pré-requisitos

Antes de mergulhar, certifique-se de ter o seguinte:

1.  Aspose.Words for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: configurado com .NET Framework.
3. Conhecimento básico de C#: Familiaridade com a sintaxe e conceitos.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Isso garante que todas as classes e métodos de que precisamos estejam prontamente disponíveis.

```csharp
using Aspose.Words;
using Aspose.Words.Comments;
```

Vamos dividir o processo em etapas simples e fáceis de seguir. Cada etapa ajudará você a entender o código e sua funcionalidade.

## Etapa 1: carregue o documento

 Para começar, carregue o documento Word que contém os comentários. Use o`Document` aula para isso.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

 Esta linha de código inicializa um novo`Document` objeto com o caminho para o seu documento do Word.

## Etapa 2: recuperar comentários

 A seguir, precisamos obter todos os comentários do documento. Usaremos o`GetChildNodes` método para recuperar uma coleção de`Comment` nós.

```csharp
NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

Este código recupera todos os comentários do documento e os armazena em um`NodeCollection`.

## Etapa 3: acesse o comentário dos pais

Para nosso exemplo, focaremos no primeiro comentário da coleção. Este será o nosso comentário dos pais.

```csharp
Comment parentComment = (Comment)comments[0];
```

 Aqui, estamos lançando o primeiro nó da coleção para um`Comment` objeto.

## Etapa 4: repetir as respostas

 Agora, vamos percorrer as respostas ao comentário pai. Usaremos um`foreach` loop para iterar sobre cada resposta.

```csharp
foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Neste loop, imprimimos o ID do comentário ancestral e seu status (concluído ou não). Em seguida, marcamos cada resposta como concluída.

## Etapa 5: salve o documento

Finalmente, salve o documento modificado em seu diretório.

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

Este código salva as alterações em um novo documento, garantindo que o arquivo original permaneça intacto.

## Conclusão

Lidar com comentários em documentos do Word não precisa ser uma tarefa manual. Com Aspose.Words for .NET, você pode automatizar o processo, economizando tempo e reduzindo erros. Siga este guia para resolver e responder com eficiência aos comentários em seus documentos.

## Perguntas frequentes

### Posso automatizar outras tarefas relacionadas a comentários com Aspose.Words for .NET?  
Sim, você pode automatizar várias tarefas, como adicionar, excluir e modificar comentários.

### O Aspose.Words for .NET é compatível com o .NET Core?  
Sim, Aspose.Words for .NET oferece suporte a .NET Framework e .NET Core.

### Como posso obter uma avaliação gratuita do Aspose.Words for .NET?  
 Você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).

### Posso usar o Aspose.Words for .NET para trabalhar com outros tipos de documentos?  
Sim, Aspose.Words suporta vários formatos, incluindo DOCX, PDF, HTML e muito mais.

### Onde posso encontrar documentação detalhada para Aspose.Words for .NET?  
 Você pode acessar a documentação[aqui](https://reference.aspose.com/words/net/).