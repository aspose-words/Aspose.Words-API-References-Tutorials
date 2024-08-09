---
title: Insira objeto Ole em documento do Word como ícone
linktitle: Insira objeto Ole em documento do Word como ícone
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um objeto OLE como um ícone em documentos do Word usando Aspose.Words for .NET. Siga nosso guia passo a passo para aprimorar seus documentos.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---
## Introdução

Você já precisou incorporar um objeto OLE, como uma apresentação do PowerPoint ou uma planilha do Excel, em um documento do Word, mas queria que ele aparecesse como um pequeno ícone em vez de um objeto completo? Bem, você está no lugar certo! Neste tutorial, orientaremos você sobre como inserir um objeto OLE como um ícone em um documento do Word usando Aspose.Words for .NET. Ao final deste guia, você será capaz de integrar perfeitamente objetos OLE em seus documentos, tornando-os mais interativos e visualmente atraentes.

## Pré-requisitos

Antes de mergulharmos nos detalhes essenciais, vamos cobrir o que você precisa:

1.  Aspose.Words for .NET: Certifique-se de ter o Aspose.Words for .NET instalado. Se você ainda não o instalou, você pode baixá-lo no site[Página de lançamentos do Aspose](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: você precisa de um ambiente de desenvolvimento integrado (IDE) como o Visual Studio.
3. Conhecimento básico de C#: Um conhecimento básico de programação C# será útil.

## Importar namespaces

Primeiro, você precisa importar os namespaces necessários. Isso é essencial para acessar as funções da biblioteca Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Etapa 1: crie um novo documento

Para começar, você precisa criar uma nova instância de documento do Word.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Este trecho de código inicializa um novo documento do Word e um objeto DocumentBuilder que é usado para construir o conteúdo do documento.

## Etapa 2: inserir objeto OLE como ícone

 Agora vamos inserir o objeto OLE como um ícone. O`InsertOleObjectAsIcon` O método da classe DocumentBuilder é usado para esse propósito.

```csharp
builder.InsertOleObjectAsIcon("path_to_your_presentation.pptx", false, "path_to_your_icon.ico", "My embedded file");
```

Vamos analisar este método:
- `"path_to_your_presentation.pptx"`: este é o caminho para o objeto OLE que você deseja incorporar.
- `false` : este parâmetro booleano especifica se o objeto OLE deve ser exibido como um ícone. Como queremos um ícone, nós o definimos como`false`.
- `"path_to_your_icon.ico"`: este é o caminho para o arquivo de ícone que você deseja usar para o objeto OLE.
- `"My embedded file"`: Este é o rótulo que aparecerá abaixo do ícone.

## Etapa 3: salve o documento

Finalmente, você precisa salvar o documento. Escolha o diretório onde deseja salvar seu arquivo.

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Esta linha de código salva o documento no caminho especificado.

## Conclusão

Parabéns! Você aprendeu com sucesso como inserir um objeto OLE como um ícone em um documento do Word usando Aspose.Words for .NET. Essa técnica não só ajuda a incorporar objetos complexos, mas também mantém seu documento organizado e profissional.

## Perguntas frequentes

### Posso usar diferentes tipos de objetos OLE com este método?

Sim, você pode incorporar vários tipos de objetos OLE, como planilhas do Excel, apresentações do PowerPoint e até PDFs.

### Como faço para obter uma avaliação gratuita do Aspose.Words for .NET?

 Você pode obter um teste gratuito no[Página de lançamentos do Aspose](https://releases.aspose.com/).

### O que é um objeto OLE?

OLE (Object Linking and Embedding) é uma tecnologia desenvolvida pela Microsoft que permite incorporar e vincular documentos e outros objetos.

### Preciso de uma licença para usar o Aspose.Words for .NET?

 Sim, Aspose.Words for .NET requer uma licença. Você pode comprá-lo no[Aspose página de compra](https://purchase.aspose.com/buy) ou obter um[licença temporária](https://purchase.aspose.com/temporary-license/) para avaliação.

### Onde posso encontrar mais tutoriais sobre Aspose.Words for .NET?

 Você pode encontrar mais tutoriais e documentação no[Página de documentação do Aspose](https://reference.aspose.com/words/net/).