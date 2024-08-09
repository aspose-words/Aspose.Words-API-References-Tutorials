---
title: Enumerar propriedades
linktitle: Enumerar propriedades
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como enumerar propriedades em um documento do Word usando Aspose.Words for .NET com este guia passo a passo. Perfeito para desenvolvedores de todos os níveis de habilidade.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/enumerate-properties/
---
## Introdução

Quer trabalhar com documentos do Word programaticamente? Aspose.Words for .NET é uma ferramenta poderosa que pode ajudá-lo a conseguir exatamente isso. Hoje, mostrarei como enumerar propriedades de um documento do Word usando Aspose.Words for .NET. Quer você seja iniciante ou tenha alguma experiência, este guia irá detalhar tudo passo a passo de uma maneira coloquial e fácil de seguir.

## Pré-requisitos

Antes de mergulharmos no tutorial, há algumas coisas que você precisa para começar:

-  Aspose.Words para .NET: você pode[baixe aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: Visual Studio é recomendado, mas você pode usar qualquer IDE C#.
- Conhecimento básico de C#: uma compreensão fundamental de C# o ajudará a acompanhar.

Agora, vamos começar!

## Etapa 1: configurando seu projeto

Primeiramente, você precisa configurar seu projeto no Visual Studio.

1. Crie um novo projeto: abra o Visual Studio e crie um novo projeto de aplicativo de console.
2. Instale o Aspose.Words para .NET: Use o NuGet Package Manager para instalar o Aspose.Words para .NET. Clique com o botão direito do mouse em seu projeto no Solution Explorer, selecione "Gerenciar pacotes NuGet" e pesquise "Aspose.Words". Instale o pacote.

## Etapa 2: importar namespaces

Para trabalhar com Aspose.Words, você precisa importar os namespaces necessários. Adicione o seguinte no topo do seu arquivo Program.cs:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Properties;
```

## Etapa 3: carregue seu documento

A seguir, vamos carregar o documento Word com o qual deseja trabalhar. Para este exemplo, usaremos um documento chamado "Properties.docx" localizado no diretório do seu projeto.

1. Definir o caminho do documento: Especifique o caminho para o seu documento.
2.  Carregue o documento: use o Aspose.Words`Document` classe para carregar o documento.

Aqui está o código:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

## Etapa 4: exibir o nome do documento

Depois que o documento for carregado, você pode querer exibir seu nome. Aspose.Words fornece uma propriedade para isso:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
```

## Etapa 5: enumerar propriedades integradas

Propriedades integradas são propriedades de metadados predefinidas pelo Microsoft Word. Isso inclui o título, autor e muito mais.

1.  Acesse as propriedades integradas: use o`BuiltInDocumentProperties` coleção.
2. Loop Through Properties: Itere pelas propriedades e exiba seus nomes e valores.

Aqui está o código:

```csharp
Console.WriteLine("2. Built-in Properties");

foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
    Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
```

## Etapa 6: enumerar propriedades personalizadas

Propriedades customizadas são propriedades de metadados definidas pelo usuário. Pode ser qualquer coisa que você queira adicionar ao seu documento.

1.  Acesse propriedades personalizadas: use o`CustomDocumentProperties` coleção.
2. Loop Through Properties: Itere pelas propriedades e exiba seus nomes e valores.

Aqui está o código:

```csharp
Console.WriteLine("3. Custom Properties");

foreach (DocumentProperty prop in doc.CustomDocumentProperties)
    Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
```

## Conclusão

aí está! Você enumerou com êxito as propriedades internas e personalizadas de um documento do Word usando Aspose.Words for .NET. Esta é apenas a ponta do iceberg quando se trata do que você pode fazer com o Aspose.Words. Esteja você automatizando a geração de documentos ou manipulando documentos complexos, o Aspose.Words oferece um rico conjunto de recursos para tornar sua vida mais fácil.

## Perguntas frequentes

### Posso adicionar novas propriedades a um documento?
 Sim, você pode adicionar novas propriedades personalizadas usando o`CustomDocumentProperties` coleção.

### O uso do Aspose.Words é gratuito?
 Aspose.Words oferece um[teste gratuito](https://releases.aspose.com/) e diferente[opções de compra](https://purchase.aspose.com/buy).

### Como obtenho suporte para Aspose.Words?
 Você pode obter suporte da comunidade Aspose[aqui](https://forum.aspose.com/c/words/8).

### Posso usar o Aspose.Words com outras linguagens .NET?
Sim, Aspose.Words oferece suporte a várias linguagens .NET, incluindo VB.NET.

### Onde posso encontrar mais exemplos?
 Confira o[Documentação do Aspose.Words para .NET](https://reference.aspose.com/words/net/) para mais exemplos e informações detalhadas.
