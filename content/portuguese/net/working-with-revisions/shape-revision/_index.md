---
title: Revisão de forma
linktitle: Revisão de forma
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como lidar com revisões de formas em documentos do Word usando Aspose.Words for .NET com este guia completo. Domine o rastreamento de alterações, a inserção de formas e muito mais.
type: docs
weight: 10
url: /pt/net/working-with-revisions/shape-revision/
---
## Introdução

Editar documentos do Word programaticamente pode ser uma tarefa difícil, especialmente quando se trata de lidar com formas. Esteja você criando relatórios, projetando modelos ou simplesmente automatizando a criação de documentos, a capacidade de rastrear e gerenciar revisões de formas é crucial. Aspose.Words for .NET oferece uma API poderosa para tornar esse processo contínuo e eficiente. Neste tutorial, nos aprofundaremos nas especificidades da revisão de formas em documentos do Word, garantindo que você tenha as ferramentas e o conhecimento para gerenciar seus documentos com facilidade.

## Pré-requisitos

Antes de mergulharmos no código, vamos garantir que você tenha tudo o que precisa:

-  Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words instalada. Você pode[baixe aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: você deve ter um ambiente de desenvolvimento configurado, como o Visual Studio.
- Compreensão básica de C#: Familiaridade com a linguagem de programação C# e conceitos básicos de programação orientada a objetos.
- Documento Word: Um documento Word para trabalhar, ou você pode criar um durante o tutorial.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários. Eles nos fornecerão acesso às classes e métodos necessários para lidar com documentos e formas do Word.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Etapa 1: configurando seu diretório de documentos

Antes de começarmos a trabalhar com formas, precisamos definir o caminho para o nosso diretório de documentos. É aqui que salvaremos nossos documentos modificados.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Criando um Novo Documento

Vamos criar um novo documento Word onde inseriremos e revisaremos formas.

```csharp
Document doc = new Document();
```

## Etapa 3: inserir uma forma embutida

Começaremos inserindo uma forma embutida em nosso documento sem rastrear revisões. Uma forma embutida é aquela que flui com o texto.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Etapa 4: começando a rastrear revisões

Para rastrear alterações em nosso documento, precisamos habilitar o rastreamento de revisões. Isso é essencial para identificar modificações feitas nas formas.

```csharp
doc.StartTrackRevisions("John Doe");
```

## Etapa 5: Inserindo Outra Forma com Revisões

Agora que o rastreamento de revisão está habilitado, vamos inserir outra forma. Desta vez, quaisquer alterações serão rastreadas.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Etapa 6: Recuperando e Modificando Formas

Podemos recuperar todas as formas do documento e modificá-las conforme necessário. Aqui, pegaremos as formas e removeremos a primeira.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## Etapa 7: salvando o documento

Depois de fazer nossas alterações, precisamos salvar o documento. Isso garante que todas as revisões e modificações sejam armazenadas.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## Etapa 8: Tratamento de revisões de movimentação de forma

Quando uma forma é movida, o Aspose.Words rastreia isso como uma revisão. Isso significa que haverá duas instâncias da forma: uma em seu local original e outra em seu novo local.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## Conclusão

E aí está! Você aprendeu com sucesso como lidar com revisões de forma em documentos do Word usando Aspose.Words for .NET. Esteja você gerenciando modelos de documentos, automatizando relatórios ou simplesmente acompanhando alterações, essas habilidades são inestimáveis. Seguindo este guia passo a passo, você não apenas dominará o básico, mas também obterá informações sobre técnicas mais avançadas de manuseio de documentos.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar e converter documentos do Word programaticamente usando C#.

### Posso rastrear alterações feitas em outros elementos de um documento do Word?
Sim, Aspose.Words for .NET oferece suporte ao rastreamento de alterações em vários elementos, incluindo texto, tabelas e muito mais.

### Como posso obter uma avaliação gratuita do Aspose.Words for .NET?
 Você pode obter uma avaliação gratuita do Aspose.Words for .NET[aqui](https://releases.aspose.com/).

### É possível aceitar ou rejeitar revisões programaticamente?
Sim, Aspose.Words for .NET fornece métodos para aceitar ou rejeitar revisões programaticamente.

### Posso usar Aspose.Words for .NET com outras linguagens .NET além de C#?
Absolutamente! Aspose.Words for .NET pode ser usado com qualquer linguagem .NET, incluindo VB.NET e F#.