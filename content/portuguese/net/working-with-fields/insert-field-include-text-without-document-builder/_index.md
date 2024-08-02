---
title: Inserir campo incluir texto sem construtor de documentos
linktitle: Inserir FieldIncludeText sem o Document Builder
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um FieldIncludeText sem usar DocumentBuilder em Aspose.Words for .NET com nosso guia passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-field-include-text-without-document-builder/
---
## Introdução

No mundo da automação e manipulação de documentos, Aspose.Words for .NET se destaca como uma ferramenta poderosa. Hoje, vamos mergulhar em um guia detalhado sobre como inserir um FieldIncludeText sem usar o DocumentBuilder. Este tutorial irá guiá-lo passo a passo pelo processo, garantindo que você entenda cada parte do código e sua finalidade.

## Pré-requisitos

Antes de mergulharmos no código, vamos ter certeza de que você tem tudo o que precisa:

1.  Aspose.Words for .NET: Certifique-se de ter a versão mais recente instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento .NET: qualquer IDE compatível com .NET, como Visual Studio.
3. Conhecimento básico de C#: A familiaridade com a programação C# o ajudará a acompanhar.

## Importar namespaces

Em primeiro lugar, precisamos importar os namespaces necessários. Esses namespaces fornecem acesso às classes e métodos necessários para manipular documentos do Word.

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

Agora, vamos dividir o exemplo em várias etapas. Cada etapa será explicada em detalhes para garantir clareza.

## Etapa 1: definir o caminho do diretório

A primeira etapa é definir o caminho para o diretório de documentos. É aqui que seus documentos do Word serão armazenados e acessados.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: crie o documento e o parágrafo

A seguir, criamos um novo documento e um parágrafo dentro desse documento. Este parágrafo conterá o campo FieldIncludeText.

```csharp
// Crie o documento e o parágrafo.
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Etapa 3: inserir campo FieldIncludeText

Agora, inserimos o campo FieldIncludeText no parágrafo. Este campo permite incluir o texto de outro documento.

```csharp
// Insira o campo FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

## Etapa 4: definir propriedades do campo

Precisamos especificar as propriedades do campo FieldIncludeText. Isso inclui definir o nome do marcador e o caminho completo do documento de origem.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = dataDir + "IncludeText.docx";
```

## Etapa 5: anexar parágrafo ao documento

Com o campo configurado, anexamos o parágrafo ao corpo da primeira seção do documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Etapa 6: Atualizar campo

Antes de salvar o documento, precisamos atualizar FieldIncludeText para garantir que ele extraia o conteúdo correto do documento de origem.

```csharp
fieldIncludeText.Update();
```

## Etapa 7: salve o documento

Finalmente, salvamos o documento no diretório especificado.

```csharp
doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

## Conclusão

E aí está! Seguindo essas etapas, você pode inserir facilmente um FieldIncludeText sem usar o DocumentBuilder no Aspose.Words for .NET. Essa abordagem fornece uma maneira simplificada de incluir conteúdo de um documento em outro, tornando as tarefas de automação de documentos muito mais simples.

## Perguntas frequentes

### O que é Aspose.Words para .NET?  
Aspose.Words for .NET é uma biblioteca poderosa para trabalhar com documentos do Word em aplicativos .NET. Ele permite criar, editar e converter documentos de forma programática.

### Por que usar FieldIncludeText?  
FieldIncludeText é útil para incluir dinamicamente conteúdo de um documento em outro, permitindo documentos mais modulares e de fácil manutenção.

### Posso usar este método para incluir texto de outros formatos de arquivo?  
FieldIncludeText funciona especificamente com documentos do Word. Para outros formatos, você pode precisar de métodos ou classes diferentes fornecidos por Aspose.Words.

### O Aspose.Words for .NET é compatível com o .NET Core?  
Sim, Aspose.Words for .NET oferece suporte a .NET Framework, .NET Core e .NET 5/6.

### Como posso obter uma avaliação gratuita do Aspose.Words for .NET?  
 Você pode obter um teste gratuito em[aqui](https://releases.aspose.com/).