---
title: Quebrar link de encaminhamento em documento do Word
linktitle: Quebrar link de encaminhamento em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como quebrar links diretos em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET é uma biblioteca poderosa que oferece vários recursos para processamento de palavras com documentos do Microsoft Word programaticamente. Um de seus recursos úteis é a capacidade de quebrar links em um documento do Word. Neste tutorial, exploraremos o código-fonte em C# que demonstra como quebrar o link direto em um documento do Word usando Aspose.Words for .NET.

## Etapa 1: visualização do código-fonte C#

O código-fonte C# fornecido concentra-se no recurso "Break A Link" do Aspose.Words for .NET. Mostra como quebrar um link em uma forma TextBox dentro de um documento. O código apresenta diferentes cenários para quebra de links e fornece instruções claras sobre como alcançar os resultados desejados.

## Etapa 2: Configurando o documento e criando uma forma TextBox

 Para começar, precisamos configurar o documento e criar uma forma TextBox. O código a seguir inicializa uma nova instância do`Document` classe e cria uma forma de caixa de texto:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Etapa 3: interromper o link direto no TextBox

 Para quebrar um link direto no TextBox, podemos usar o`BreakForwardLink()` método. Este método quebra o link para a próxima forma na sequência. O código a seguir mostra como quebrar um link direto:

```csharp
textBox.BreakForwardLink();
```

## Etapa 4: quebrar um link direto definindo um valor nulo

 Alternativamente, podemos quebrar um link direto definindo o TextBox`Next`propriedade para`null`. Isso efetivamente remove a conexão com a próxima forma. O código a seguir demonstra essa abordagem:

```csharp
textBox. Next = null;
```

## Etapa 5: quebrar um link que leva ao TextBox

 Em alguns casos, precisamos quebrar um link que leva ao formato TextBox. Podemos conseguir isso chamando o`BreakForwardLink()` método no`Previous` formulário, que quebra o link para o TextBox. Aqui está um exemplo de como quebrar esse link:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Exemplo de código-fonte para quebrar um link com Aspose.Words for .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Quebrar link direto.
textBox.BreakForwardLink();

// Quebre um link direto definindo um valor nulo.
textBox. Next = null;

// Quebre um link que leva a esta caixa de texto.
textBox.Previous?.BreakForwardLink();
```

## Conclusão

Parabéns! Agora você aprendeu como quebrar links de redirecionamento em um documento do Word usando a biblioteca Aspose.Words para .NET. Seguindo as etapas deste guia, você conseguiu configurar o documento, criar uma forma TextBox e quebrar os links de redirecionamento usando métodos diferentes.

### Perguntas frequentes sobre link de avanço em documento do Word

#### P: Qual é a biblioteca usada para quebrar links de redirecionamento em um documento do Word usando Aspose.Words for .NET?

R: Para quebrar links de redirecionamento em um documento do Word usando Aspose.Words for .NET, a biblioteca usada é Aspose.Words for .NET.

#### P: Como quebrar um link de redirecionamento em um TextBox?

 R: Para quebrar um link direto em um TextBox, você pode usar o`BreakForwardLink()` método. Este método quebra o link para a próxima forma na sequência.

#### P: Como quebrar um link de redirecionamento definindo um valor nulo?

R: Como alternativa, você pode quebrar um link de redirecionamento definindo a opção`Next` propriedade do TextBox para`null`. Isso efetivamente remove a conexão com a próxima forma.

#### P: Como quebrar um link que leva ao TextBox?

 R: Em alguns casos você precisa quebrar um link que leva ao TextBox. Você pode conseguir isso ligando para o`BreakForwardLink()` método no`Previous` formulário, que quebra o link para o TextBox.

#### P: Podemos quebrar links de redirecionamento em outros elementos além de TextBoxes?

R: Sim, com Aspose.Words for .NET é possível quebrar links de redirecionamento em diferentes elementos como parágrafos, tabelas, imagens, etc.