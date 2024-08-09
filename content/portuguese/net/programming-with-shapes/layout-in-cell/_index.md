---
title: Layout na célula
linktitle: Layout na célula
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir o layout na célula usando Aspose.Words for .NET com este guia abrangente. Perfeito para desenvolvedores que desejam personalizar documentos do Word.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/layout-in-cell/
---
## Introdução

Se você sempre quis ajustar o layout das células da sua tabela em documentos do Word de forma programática, você está no lugar certo. Hoje, vamos nos aprofundar em como definir o layout na célula usando Aspose.Words for .NET. Veremos um exemplo prático, detalhando-o passo a passo para que você possa acompanhar com facilidade.

## Pré-requisitos

Antes de entrarmos no código, vamos garantir que você tenha tudo o que precisa:

1.  Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words for .NET instalada. Se ainda não o fez, você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: você precisará de um ambiente de desenvolvimento configurado com .NET. O Visual Studio é uma ótima opção se você estiver procurando recomendações.
3. Conhecimento básico de C#: Embora eu explique cada etapa, um entendimento básico de C# o ajudará a acompanhar com mais facilidade.
4.  Diretório de documentos: prepare um caminho de diretório onde você salvará seus documentos. Vamos nos referir a isso como`YOUR DOCUMENT DIRECTORY`.

## Importar namespaces

Para começar, certifique-se de importar os namespaces necessários para o seu projeto:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Vamos dividir o processo em etapas gerenciáveis.

## Etapa 1: crie um novo documento

 Primeiro, criaremos um novo documento Word e inicializaremos um`DocumentBuilder` objeto para nos ajudar a construir nosso conteúdo.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: iniciar uma tabela e definir o formato da linha

Começaremos a construir uma tabela e especificaremos a altura e a regra de altura para as linhas.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Etapa 3: inserir células e preencher com conteúdo

A seguir, fazemos um loop para inserir células na tabela. Para cada 7 células, encerraremos a linha para criar uma nova.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Etapa 4: adicionar um formato de marca d'água

 Agora, vamos adicionar uma marca d'água ao nosso documento. Criaremos um`Shape` objeto e definir suas propriedades.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Exiba a forma fora da célula da tabela se ela for colocada em uma célula.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Etapa 5: personalizar a aparência da marca d’água

Personalizaremos ainda mais a aparência da marca d'água definindo sua cor e propriedades de texto.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Etapa 6: inserir marca d’água no documento

Encontraremos a última execução no documento e inseriremos a marca d'água nessa posição.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Etapa 7: otimizar documento para Word 2010

Para garantir a compatibilidade, otimizaremos o documento para o Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Etapa 8: salve o documento

Finalmente, salvaremos nosso documento no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Conclusão

E aí está! Você criou com sucesso um documento do Word com um layout de tabela personalizado e adicionou uma marca d'água usando Aspose.Words for .NET. Este tutorial teve como objetivo fornecer um guia passo a passo claro para ajudá-lo a entender cada parte do processo. Com essas habilidades, agora você pode criar documentos do Word mais sofisticados e personalizados de forma programática.

## Perguntas frequentes

### Posso usar uma fonte diferente para o texto da marca d'água?
 Sim, você pode alterar a fonte definindo o`watermark.TextPath.FontFamily` propriedade para a fonte desejada.

### Como ajusto a posição da marca d’água?
 Você pode modificar o`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , e`VerticalAlignment` propriedades para ajustar a posição da marca d'água.

### É possível usar uma imagem em vez de texto como marca d'água?
 Absolutamente! Você pode criar um`Shape` com o tipo`ShapeType.Image` e defina sua imagem usando o`ImageData.SetImage` método.

### Posso criar tabelas com alturas de linha variadas?
Sim, você pode definir alturas diferentes para cada linha alterando o`RowFormat.Height` propriedade antes de inserir células nessa linha.

### Como faço para remover uma marca d'água do documento?
 Você pode remover a marca d’água localizando-a na coleção de formas do documento e chamando o método`Remove` método.