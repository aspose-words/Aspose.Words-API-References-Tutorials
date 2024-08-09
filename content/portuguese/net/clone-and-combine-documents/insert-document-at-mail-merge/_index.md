---
title: Inserir documento na mala direta
linktitle: Inserir documento na mala direta
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir documentos em campos de mala direta usando Aspose.Words for .NET neste tutorial passo a passo abrangente.
type: docs
weight: 10
url: /pt/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Introdução

Bem-vindo ao mundo da automação de documentos com Aspose.Words for .NET! Você já se perguntou como inserir documentos dinamicamente em campos específicos de um documento principal durante uma operação de mala direta? Bem, você está no lugar certo. Este tutorial irá guiá-lo passo a passo através do processo de inserção de documentos em campos de mala direta usando Aspose.Words for .NET. É como montar um quebra-cabeça, onde cada peça se encaixa perfeitamente. Então, vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Aspose.Words para .NET: você pode[baixe a versão mais recente aqui](https://releases.aspose.com/words/net/) . Se precisar comprar uma licença, você pode fazê-lo[aqui](https://purchase.aspose.com/buy) . Alternativamente, você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/) ou experimente com um[teste gratuito](https://releases.aspose.com/).
2. Ambiente de desenvolvimento: Visual Studio ou qualquer outro IDE C#.
3. Conhecimento básico de C#: A familiaridade com a programação C# tornará este tutorial muito fácil.

## Importar namespaces

Primeiramente, você precisará importar os namespaces necessários. Estes são como os blocos de construção do seu projeto.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Vamos dividir o processo em etapas gerenciáveis. Cada etapa se baseará na anterior, levando você a uma solução completa.

## Etapa 1: configurando seu diretório

Antes de começar a inserir documentos, você precisa definir o caminho para o diretório de documentos. É aqui que seus documentos são armazenados.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregando o Documento Principal

A seguir, você carregará o documento principal. Este documento contém os campos de mesclagem onde outros documentos serão inseridos.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Etapa 3: definir o retorno de chamada de mesclagem de campos

Para lidar com o processo de fusão, você precisará definir uma função de retorno de chamada. Esta função será responsável por inserir documentos nos campos de mesclagem especificados.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Etapa 4: executando a mala direta

Agora é hora de executar a mala direta. É aqui que a mágica acontece. Você especificará o campo de mesclagem e o documento que deverá ser inserido neste campo.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Etapa 5: salvando o documento

Após a conclusão da mala direta, você salvará o documento modificado. Este novo documento terá o conteúdo inserido exatamente onde você deseja.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Etapa 6: Criando o manipulador de retorno de chamada

O manipulador de retorno de chamada é uma classe que faz processamento especial para o campo de mesclagem. Ele carrega o documento especificado no valor do campo e o insere no campo de mesclagem atual.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Passo 7: Inserindo o Documento

Este método insere o documento especificado no parágrafo ou célula da tabela atual.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## Conclusão

E aí está! Você inseriu documentos com êxito em campos específicos durante uma operação de mala direta usando Aspose.Words for .NET. Esse recurso poderoso pode economizar muito tempo e esforço, especialmente ao lidar com grandes volumes de documentos. Pense nisso como ter um assistente pessoal que cuida de todo o trabalho pesado para você. Então, vá em frente e experimente. Boa codificação!

## Perguntas frequentes

### Posso inserir vários documentos em diferentes campos de mesclagem?
Sim, você pode. Basta especificar os campos de mesclagem apropriados e os caminhos de documento correspondentes no campo`MailMerge.Execute` método.

### É possível formatar o documento inserido de forma diferente do documento principal?
 Absolutamente! Você pode usar o`ImportFormatMode` parâmetro no`NodeImporter` para controlar a formatação.

### E se o nome do campo de mesclagem for dinâmico?
Você pode manipular nomes de campos de mesclagem dinâmica passando-os como parâmetros para o manipulador de retorno de chamada.

### Posso usar este método com diferentes formatos de arquivo?
Sim, Aspose.Words suporta vários formatos de arquivo, incluindo DOCX, PDF e muito mais.

### Como lidar com erros durante o processo de inserção de documentos?
Implemente o tratamento de erros em seu manipulador de retorno de chamada para gerenciar quaisquer exceções que possam ocorrer.