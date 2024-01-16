---
title: Documento do proprietário
linktitle: Documento do proprietário
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar o documento do proprietário em Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-node/owner-document/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo que ilustra como usar a funcionalidade de documento proprietário com Aspose.Words for .NET.

## Passo 1: Importe as referências necessárias
Antes de começar, certifique-se de ter importado as referências necessárias para usar Aspose.Words for .NET em seu projeto. Isso inclui importar a biblioteca Aspose.Words e adicionar os namespaces necessários ao seu arquivo de origem.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## Passo 2: Crie um novo documento
 Nesta etapa, criaremos um novo documento usando o`Document` aula.

```csharp
Document doc = new Document();
```

## Etapa 3: Crie um nó com o documento do proprietário
 Ao criar um novo nó de qualquer tipo, você deve passar o documento para o construtor. Neste exemplo, estamos criando um novo nó de parágrafo usando o documento`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## Etapa 4: verifique o nó pai e o documento do proprietário
 Agora que criamos o nó do parágrafo, podemos verificar se ele possui um nó pai e se o documento proprietário é o mesmo que`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Etapa 5: modificar as propriedades do nó com dados do documento
O relacionamento entre um nó e um documento permite o acesso e a modificação de propriedades que se referem a dados específicos do documento, como estilos ou listas. Neste exemplo, estamos definindo o nome do estilo de parágrafo como “Título 1”.

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Etapa 6: adicione o parágrafo ao documento
Agora podemos adicionar o nó do parágrafo à seção principal do documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Etapa 7: verifique o nó pai após adicionar
Após adicionar o parágrafo ao documento, verificamos novamente se ele agora possui um nó pai.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Exemplo de código-fonte para documento do proprietário com Aspose.Words for .NET

```csharp
Document doc = new Document();

// A criação de um novo nó de qualquer tipo requer um documento passado para o construtor.
Paragraph para = new Paragraph(doc);

// O novo nó de parágrafo ainda não possui pai.
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

// Mas o nó do parágrafo conhece o seu documento.
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

// O fato de um nó sempre pertencer a um documento nos permite acessar e modificar
// propriedades que fazem referência aos dados de todo o documento, como estilos ou listas.
para.ParagraphFormat.StyleName = "Heading 1";

// Agora adicione o parágrafo ao texto principal da primeira seção.
doc.FirstSection.Body.AppendChild(para);

// O nó parágrafo agora é filho do nó Corpo.
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```

### Perguntas frequentes

#### P: O que é um documento proprietário em Node.js?

R: Um documento proprietário em Node.js é o documento XML ao qual pertence um nó específico. Representa a instância do documento XML que contém o nó.

#### P: Como obter o documento do proprietário de um nó?

 R: Para obter o documento do proprietário de um nó no Node.js, você pode usar o`ownerDocument` propriedade do nó. Esta propriedade retorna o documento XML que possui o nó.

#### P: Para que é usado o documento proprietário?

R: O documento proprietário é usado para representar o contexto global de um nó em um documento XML. Ele fornece acesso a outros nós do documento e permite que operações sejam executadas neles.

#### P: Podemos modificar o documento do proprietário de um nó?

R: Na maioria dos casos, o proprietário do documento de um nó é determinado quando o nó é criado e não pode ser alterado diretamente. O documento do proprietário é uma propriedade somente leitura.

#### P: Como acessar os nós de um documento proprietário?

 R: Para acessar nós em um documento proprietário, você pode usar os métodos e propriedades fornecidos pela API XML usada em seu ambiente Node.js. Por exemplo, você pode usar métodos como`getElementsByTagName` ou`querySelector` para selecionar nós específicos no documento.