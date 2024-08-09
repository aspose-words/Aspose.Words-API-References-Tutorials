---
title: Obtenha tipos de revisão de palavras
linktitle: Obtenha tipos de revisão de palavras
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como obter tipos de revisão de palavras em um documento do Word usando Aspose.Words for .NET. Este guia passo a passo ajuda você a lidar com as revisões de documentos com eficiência.
type: docs
weight: 10
url: /pt/net/working-with-revisions/get-revision-types/
---
## Introdução

Você já se viu mergulhado em um mar de revisões de documentos, imaginando quem moveu o quê e quando? Você não está sozinho. Lidar com revisões de documentos pode ser uma tarefa tediosa, especialmente quando se lida com documentos extensos. Mas não se preocupe! Com Aspose.Words for .NET, você pode identificar e gerenciar facilmente essas revisões. Neste guia, orientaremos você em um processo passo a passo sobre como obter tipos de revisão de palavras em um documento do Word usando Aspose.Words for .NET. Então, aperte o cinto e vamos mergulhar!

## Pré-requisitos

Antes de sujarmos as mãos com algum código, há algumas coisas que você precisará:

1.  Biblioteca Aspose.Words for .NET: se ainda não o fez, baixe-o em[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: Visual Studio ou qualquer outro IDE compatível com .NET.
3. Conhecimento básico de C#: A compreensão da linguagem de programação C# será benéfica.
4.  Um documento Word com revisões: certifique-se de ter um`.docx`arquivo com alterações controladas para testar o código.

## Importar namespaces

Para começar, você precisará importar os namespaces necessários em seu projeto C#. Isso permitirá que você acesse as funcionalidades fornecidas pelo Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

Vamos dividir o exemplo em várias etapas para melhor compreensão e implementação.

## Etapa 1: configure seu diretório de documentos

Em primeiro lugar, você precisa definir o caminho para o diretório de documentos. É aqui que o seu documento Word com revisões estará localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para sua pasta de documentos.

## Etapa 2: carregue seu documento do Word

Em seguida, você precisa carregar o documento Word em seu projeto. Este documento deverá conter as revisões que você deseja analisar.

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

 Certifique-se de que o arquivo`Revisions.docx` existe no diretório especificado.

## Etapa 3: acesse a coleção de parágrafos

Agora que seu documento foi carregado, você precisa acessar os parágrafos da primeira seção do corpo do documento. Isso o ajudará a percorrer cada parágrafo para verificar se há revisões.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## Etapa 4: iterar pelos parágrafos e verificar se há revisões

É aqui que a mágica acontece. Você percorrerá cada parágrafo e verificará se ele foi movido (excluído ou inserido).

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

 Este loop percorre cada parágrafo e usa o`IsMoveFromRevision`e`IsMoveToRevision` propriedades para determinar se o parágrafo foi movido (excluído) ou movido (inserido).

## Conclusão

E aí está! Com apenas algumas linhas de código, você pode identificar facilmente os tipos de revisões em seu documento Word usando Aspose.Words for .NET. Esta poderosa biblioteca facilita muito o manuseio de revisões de documentos, permitindo que você se concentre em tarefas mais importantes. 

## Perguntas frequentes

### Posso usar o Aspose.Words for .NET para rastrear alterações feitas por usuários específicos?

Sim, Aspose.Words for .NET fornece funcionalidade para acessar detalhes da revisão, incluindo o autor das alterações.

### Existe um teste gratuito disponível para Aspose.Words for .NET?

 Absolutamente! Você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Como posso aplicar uma licença temporária do Aspose.Words for .NET?

 Você pode solicitar e aplicar uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso encontrar documentação mais detalhada para Aspose.Words for .NET?

 A documentação detalhada está disponível no site[Aspor site](https://reference.aspose.com/words/net/).

### Posso usar o Aspose.Words for .NET em um projeto não comercial?

Sim, o Aspose.Words for .NET pode ser usado em projetos comerciais e não comerciais, mas certifique-se de verificar os termos de licenciamento.