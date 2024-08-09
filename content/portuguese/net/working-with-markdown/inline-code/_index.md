---
title: Código embutido
linktitle: Código embutido
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como aplicar estilos de código embutido em documentos do Word usando Aspose.Words for .NET. Este tutorial cobre crases únicos e múltiplos para formatação de código.
type: docs
weight: 10
url: /pt/net/working-with-markdown/inline-code/
---
## Introdução

Se você estiver trabalhando na geração ou manipulação de documentos do Word de forma programática, talvez seja necessário formatar o texto para se parecer com o código. Seja para documentação ou trechos de código em um relatório, o Aspose.Words for .NET fornece uma maneira robusta de lidar com estilos de texto. Neste tutorial, vamos nos concentrar em como aplicar estilos de código embutido ao texto usando Aspose.Words. Exploraremos como definir e usar estilos personalizados para crases únicos e múltiplos, fazendo com que seus segmentos de código se destaquem claramente em seus documentos.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Biblioteca Aspose.Words para .NET: Certifique-se de ter o Aspose.Words instalado em seu ambiente .NET. Você pode baixá-lo no[Página de lançamentos do Aspose.Words for .NET](https://releases.aspose.com/words/net/).

2. Conhecimento básico de programação .NET: Este guia pressupõe que você tenha um conhecimento fundamental de programação C# e .NET.

3. Ambiente de desenvolvimento: você deve ter um ambiente de desenvolvimento .NET configurado, como o Visual Studio, onde você pode escrever e executar código C#.

## Importar namespaces

Para começar a usar Aspose.Words em seu projeto, você precisará importar os namespaces necessários. Veja como você faz isso:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Vamos dividir o processo em etapas claras:

## Etapa 1: inicializar o documento e o DocumentBuilder

 Primeiro, você precisa criar um novo documento e um`DocumentBuilder` exemplo. O`DocumentBuilder`class ajuda você a adicionar conteúdo e formatá-lo em um documento do Word.

```csharp
// Inicialize o DocumentBuilder com o novo documento.
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: adicionar estilo de código embutido com um backtick

Nesta etapa, definiremos um estilo para código embutido com um único crase. Este estilo formatará o texto para se parecer com o código embutido.

### Defina o estilo

```csharp
// Defina um novo estilo de caractere para código embutido com um crase.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
inlineCode1BackTicks.Font.Name = "Courier New"; // Uma fonte típica para código.
inlineCode1BackTicks.Font.Size = 10.5; // Tamanho da fonte do código embutido.
inlineCode1BackTicks.Font.Color = System.Drawing.Color.Blue; // Cor do texto do código.
inlineCode1BackTicks.Font.Bold = true; // Deixe o texto do código em negrito.
```

### Aplicar o estilo

Agora, você pode aplicar esse estilo ao texto do seu documento.

```csharp
// Use o DocumentBuilder para inserir texto com o estilo de código embutido.
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");
```

## Etapa 3: adicionar estilo de código embutido com três crases

A seguir, definiremos um estilo para código embutido com três crases, que normalmente é usado para blocos de código multilinhas.

### Defina o estilo

```csharp
// Defina um novo estilo de caractere para código embutido com três crases.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
inlineCode3BackTicks.Font.Name = "Courier New"; // Fonte consistente para código.
inlineCode3BackTicks.Font.Size = 10.5; // Tamanho da fonte do bloco de código.
inlineCode3BackTicks.Font.Color = System.Drawing.Color.Green; //Cor diferente para visibilidade.
inlineCode3BackTicks.Font.Bold = true; // Mantenha-o em negrito para dar ênfase.
```

### Aplicar o estilo

Aplique este estilo ao texto para formatá-lo como um bloco de código multilinha.

```csharp
// Aplique o estilo ao bloco de código.
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```

## Conclusão

Formatar texto como código embutido em documentos do Word usando Aspose.Words for .NET é simples quando você conhece as etapas. Ao definir e aplicar estilos personalizados com crases únicos ou múltiplos, você pode fazer com que seus trechos de código se destaquem claramente. Este método é particularmente útil para documentação técnica ou qualquer documento onde a legibilidade do código seja essencial.

Sinta-se à vontade para experimentar diferentes estilos e opções de formatação para melhor atender às suas necessidades. Aspose.Words oferece ampla flexibilidade, permitindo que você personalize bastante a aparência do seu documento.

## Perguntas frequentes

### Posso usar fontes diferentes para estilos de código embutido?
Sim, você pode usar qualquer fonte que atenda às suas necessidades. Fontes como "Courier New" são normalmente usadas para código devido à sua natureza monoespaçada.

### Como altero a cor do texto do código embutido?
 Você pode alterar a cor definindo o`Font.Color` propriedade do estilo para qualquer`System.Drawing.Color`.

### Posso aplicar vários estilos ao mesmo texto?
No Aspose.Words, você só pode aplicar um estilo por vez. Se precisar combinar estilos, considere criar um novo estilo que incorpore toda a formatação desejada.

### Como aplico estilos ao texto existente em um documento?
 Para aplicar estilos ao texto existente, você precisa primeiro selecionar o texto e depois aplicar o estilo desejado usando o botão`Font.Style` propriedade.

### Posso usar Aspose.Words para outros formatos de documentos?
Aspose.Words foi projetado especificamente para documentos do Word. Para outros formatos, pode ser necessário usar bibliotecas diferentes ou converter os documentos para um formato compatível.