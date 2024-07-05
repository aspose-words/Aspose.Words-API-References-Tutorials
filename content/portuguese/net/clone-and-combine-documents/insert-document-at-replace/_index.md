---
title: Inserir documento em substituição
linktitle: Inserir documento em substituição
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir perfeitamente um documento do Word em outro usando Aspose.Words for .NET com nosso guia passo a passo detalhado. Perfeito para desenvolvedores que buscam agilizar o processamento de documentos.
type: docs
weight: 10
url: /pt/net/clone-and-combine-documents/insert-document-at-replace/
---
## Introdução

Olá, maestros de documentos! Você já se viu mergulhado no código, tentando descobrir como inserir um documento do Word em outro perfeitamente? Não tenha medo, porque hoje estamos mergulhando no mundo do Aspose.Words for .NET para tornar essa tarefa muito fácil. Percorreremos um guia passo a passo detalhado sobre como usar esta poderosa biblioteca para inserir documentos em pontos específicos durante uma operação de localização e substituição. Pronto para se tornar um assistente do Aspose.Words? Vamos começar!

## Pré-requisitos

Antes de entrarmos no código, há algumas coisas que você precisa ter em mente:

-  Visual Studio: certifique-se de ter o Visual Studio instalado em sua máquina. Se você ainda não o possui, pode baixá-lo em[aqui](https://visualstudio.microsoft.com/).
-  Aspose.Words para .NET: você precisará da biblioteca Aspose.Words. Você pode obtê-lo no[Aspor site](https://releases.aspose.com/words/net/).
- Conhecimento básico de C#: um conhecimento básico de C# e .NET o ajudará a acompanhar este tutorial.

Tudo bem, com isso resolvido, vamos sujar as mãos com algum código!

## Importar namespaces

Primeiramente, precisamos importar os namespaces necessários para trabalhar com Aspose.Words. É como reunir todas as suas ferramentas antes de iniciar um projeto. Adicione-os usando diretivas na parte superior do seu arquivo C#:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Agora que estabelecemos nossos pré-requisitos, vamos dividir o processo em pequenas etapas. Cada passo é crucial e nos aproximará de nosso objetivo.

## Etapa 1: configurando o diretório de documentos

Primeiro, precisamos especificar o diretório onde nossos documentos estão armazenados. É como preparar o cenário antes da grande apresentação.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o seu diretório. É aqui que seus documentos viverão e respirarão.

## Etapa 2: carregue o documento principal

A seguir, carregamos o documento principal no qual queremos inserir outro documento. Pense nisso como o nosso palco principal onde toda a ação acontecerá.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Este código carrega o documento principal do diretório especificado.

## Etapa 3: definir opções de localização e substituição

Para encontrar o local específico onde queremos inserir nosso documento, usamos a funcionalidade localizar e substituir. É como usar um mapa para encontrar o local exato para nossa nova adição.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Aqui, estamos definindo a direção para trás e especificando um manipulador de retorno de chamada personalizado que definiremos a seguir.

## Etapa 4: execute a operação de substituição

Agora, dizemos ao nosso documento principal para procurar um texto de espaço reservado específico e substituí-lo por nada, enquanto usamos nosso retorno de chamada personalizado para inserir outro documento.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Este código executa a operação localizar e substituir e, em seguida, salva o documento atualizado.

## Etapa 5: crie um manipulador de retorno de chamada de substituição personalizado

Nosso manipulador de retorno de chamada personalizado é onde a mágica acontece. Este manipulador definirá como será realizada a inserção do documento durante a operação de localização e substituição.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Insira um documento após o parágrafo que contém o texto correspondente.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Remova o parágrafo com o texto correspondente.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Aqui carregamos o documento a ser inserido e depois chamamos um método auxiliar para realizar a inserção.

## Etapa 6: Definir o método de inserção de documento

A peça final do nosso quebra-cabeça é o método que realmente insere o documento no local especificado.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Percorra todos os nós de nível de bloco no corpo da seção,
		// em seguida, clone e insira cada nó que não seja o último parágrafo vazio de uma seção.
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

Este método se encarrega de importar os nós do documento a ser inserido e colocá-los no lugar certo do documento principal.

## Conclusão

E aí está! Um guia completo para inserir um documento em outro usando Aspose.Words for .NET. Seguindo essas etapas, você pode automatizar facilmente as tarefas de montagem e manipulação de documentos. Esteja você construindo um sistema de gerenciamento de documentos ou apenas precise agilizar seu fluxo de trabalho de processamento de documentos, Aspose.Words é seu companheiro de confiança.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para manipular documentos do Word programaticamente. Ele permite criar, modificar, converter e processar documentos do Word com facilidade.

### Posso inserir vários documentos de uma vez?
Sim, você pode modificar o manipulador de retorno de chamada para lidar com múltiplas inserções iterando em uma coleção de documentos.

### Existe um teste gratuito disponível?
 Absolutamente! Você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).

### Como obtenho suporte para Aspose.Words?
Você pode obter suporte visitando o[Fórum Aspose.Words](https://forum.aspose.com/c/words/8).

### Posso manter a formatação do documento inserido?
 Sim o`NodeImporter` classe permite especificar como a formatação é tratada ao importar nós de um documento para outro.