---
title: Mapeamento Xml inicial do intervalo de tags do documento estruturado
linktitle: Mapeamento Xml inicial do intervalo de tags do documento estruturado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como vincular dinamicamente dados XML a tags de documentos estruturados no Word usando Aspose.Words for .NET. Siga nosso guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## Introdução

Você já quis inserir dados XML dinamicamente em um documento do Word? Bem, você está com sorte! Aspose.Words for .NET torna essa tarefa muito fácil. Neste tutorial, estamos nos aprofundando no mapeamento XML de início de intervalo de tags de documento estruturado. Esse recurso permite vincular partes XML personalizadas a controles de conteúdo, garantindo que o conteúdo do seu documento seja atualizado perfeitamente com seus dados XML. Pronto para transformar seus documentos em obras-primas dinâmicas.

## Pré-requisitos

Antes de passarmos para a parte de codificação, vamos ter certeza de que você tem tudo o que precisa:

1.  Biblioteca Aspose.Words for .NET: certifique-se de ter a versão mais recente. Você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: Visual Studio ou qualquer outro IDE que suporte C#.
3. Conhecimento básico de C#: Familiaridade com programação C# é obrigatória.
4. Documento do Word: um exemplo de documento do Word para trabalhar.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Isso garantirá que tenhamos acesso a todas as classes e métodos necessários no Aspose.Words for .NET.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## Etapa 1: configure seu diretório de documentos

Todo projeto precisa de uma base, certo? Aqui, configuramos o caminho para o diretório do seu documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregue o documento do Word

A seguir, carregamos o documento Word. Este é o documento onde inseriremos nossos dados XML.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## Etapa 3: adicionar parte XML personalizada

Precisamos construir uma parte XML contendo os dados que queremos inserir e adicioná-los à coleção CustomXmlPart do documento. Esta parte XML personalizada servirá como fonte de dados para nossas tags de documentos estruturados.

### Criando uma parte XML

Primeiro, gere um ID exclusivo para a parte XML e defina seu conteúdo.

```csharp
// Construa uma parte XML que contenha dados e adicione-a à coleção CustomXmlPart do documento.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### Verifique o conteúdo da parte XML

Para garantir que a parte XML seja adicionada corretamente, imprimimos seu conteúdo.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## Etapa 4: crie uma tag de documento estruturado

Uma Tag de Documento Estruturado (SDT) é um controle de conteúdo que pode ser vinculado a uma parte XML. Aqui, criamos um SDT que exibirá o conteúdo de nossa parte XML personalizada.

Primeiro, localize o início do intervalo SDT no documento.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Etapa 5: definir o mapeamento XML para o SDT

Agora é hora de vincular nossa parte XML ao SDT. Ao definir um mapeamento XML, especificamos qual parte dos dados XML deve ser exibida no SDT.

 O XPath aponta para o elemento específico na parte XML que queremos exibir. Aqui apontamos para o segundo`<text>` elemento dentro do`<root>` elemento.

```csharp
// Defina um mapeamento para nossa StructuredDocumentTag
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Etapa 6: salve o documento

Por fim, salve o documento para ver as alterações em ação. O SDT no documento do Word agora exibirá o conteúdo XML especificado.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Conclusão

aí está! Você mapeou com êxito uma parte XML para uma tag de documento estruturado em um documento do Word usando Aspose.Words for .NET. Este poderoso recurso permite criar documentos dinâmicos e baseados em dados sem esforço. Esteja você gerando relatórios, faturas ou qualquer outro tipo de documento, o mapeamento XML pode agilizar significativamente seu fluxo de trabalho.

## Perguntas frequentes

### O que é uma tag de documento estruturado no Word?
Tags de documentos estruturados, também conhecidas como controles de conteúdo, são contêineres para tipos específicos de conteúdo em documentos do Word. Eles podem ser usados para vincular dados, restringir a edição ou orientar os usuários na criação de documentos.

### Como posso atualizar o conteúdo da parte XML dinamicamente?
 Você pode atualizar o conteúdo da parte XML modificando o arquivo`xmlPartContent` string antes de adicioná-lo ao documento. Simplesmente atualize a string com os novos dados e adicione-a ao`CustomXmlParts` coleção.

### Posso vincular várias partes XML a diferentes SDTs no mesmo documento?
Sim, você pode vincular várias partes XML a diferentes SDTs no mesmo documento. Cada SDT pode ter sua própria parte XML exclusiva e mapeamento XPath.

### É possível mapear estruturas XML complexas para SDTs?
Absolutamente! Você pode mapear estruturas XML complexas para SDTs usando expressões XPath detalhadas que apontam com precisão para os elementos desejados na parte XML.

### Como posso remover uma parte XML de um documento?
 Você pode remover uma parte XML chamando o método`Remove` método no`CustomXmlParts` coleta, passando`xmlPartId` da parte XML que você deseja remover.