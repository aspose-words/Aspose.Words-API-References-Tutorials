---
title: Formatar tabela e célula com bordas diferentes
linktitle: Formatar tabela e célula com bordas diferentes
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como formatar tabelas e células com bordas diferentes usando Aspose.Words for .NET. Aprimore seus documentos do Word com estilos de tabela e sombreamento de células personalizados.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---
## Introdução

Você já tentou deixar seus documentos do Word mais profissionais personalizando as bordas das tabelas e células? Se não, você terá uma surpresa! Este tutorial irá orientá-lo no processo de formatação de tabelas e células com bordas diferentes usando Aspose.Words for .NET. Imagine ter o poder de alterar a aparência das suas tabelas com apenas algumas linhas de código. Intrigado? Vamos nos aprofundar e explorar como você pode conseguir isso com facilidade.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
- Uma compreensão básica da programação C#.
- Visual Studio instalado em seu computador.
-  Biblioteca Aspose.Words para .NET. Se você ainda não instalou, pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
-  Uma licença Aspose válida. Você pode obter uma avaliação gratuita ou uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).

## Importar namespaces

Para trabalhar com Aspose.Words for .NET, você precisa importar os namespaces necessários para o seu projeto. Adicione o seguinte usando diretivas na parte superior do seu arquivo de código:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System.Drawing;
```

## Etapa 1: inicializar o documento e o DocumentBuilder

Primeiro, você precisa criar um novo documento e inicializar o DocumentBuilder, que auxilia na construção do conteúdo do documento. 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: comece a criar uma tabela

A seguir, use o DocumentBuilder para começar a criar uma tabela e inserir a primeira célula.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

## Etapa 3: definir bordas da tabela

Defina as bordas de toda a tabela. Esta etapa garante que todas as células da tabela tenham um estilo de borda consistente, a menos que seja especificado de outra forma.

```csharp
// Defina as bordas de toda a tabela.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
```

## Etapa 4: aplicar sombreamento celular

Aplique sombreamento às células para torná-las visualmente distintas. Neste exemplo, definiremos a cor de fundo da primeira célula como vermelho.


```csharp
// Defina o sombreamento celular para esta célula.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
```

## Etapa 5: insira outra célula com sombreamento diferente

Insira a segunda célula e aplique uma cor de sombreamento diferente. Isso torna a tabela mais colorida e fácil de ler.

```csharp
builder.InsertCell();
// Especifique um sombreamento de célula diferente para a segunda célula.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
```

## Etapa 6: Limpar formatação de células

Limpe a formatação das células das operações anteriores para garantir que as próximas células não herdem os mesmos estilos.


```csharp
// Limpe a formatação das células das operações anteriores.
builder.CellFormat.ClearFormatting();
```

## Etapa 7: personalizar bordas para células específicas

Personalize as bordas de células específicas para destacá-las. Aqui, definiremos bordas maiores para a primeira célula da nova linha.

```csharp
builder.InsertCell();
// Crie bordas maiores para a primeira célula desta linha. Isso será diferente
// em comparação com as bordas definidas para a mesa.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
```

## Etapa 8: inserir a célula final

Insira a célula final e certifique-se de que sua formatação esteja limpa, para que ela utilize os estilos padrão da tabela.

```csharp
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Etapa 9: salve o documento

Finalmente, salve o documento no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusão

E aí está! Você acabou de aprender como formatar tabelas e células com bordas diferentes usando Aspose.Words for .NET. Ao personalizar as bordas da tabela e o sombreamento das células, você pode melhorar significativamente o apelo visual dos seus documentos. Então vá em frente, experimente estilos diferentes e faça com que seus documentos se destaquem!

## Perguntas frequentes

### Posso usar estilos de borda diferentes para cada célula?
 Sim, você pode definir diferentes estilos de borda para cada célula usando o`CellFormat.Borders` propriedade.

### Como posso remover todas as bordas de uma tabela?
 Você pode remover todas as bordas definindo o estilo da borda como`LineStyle.None`.

### É possível definir cores de borda diferentes para cada célula?
 Absolutamente! Você pode personalizar a cor da borda de cada célula usando o`CellFormat.Borders.Color` propriedade.

### Posso usar imagens como plano de fundo de células?
Embora Aspose.Words não suporte diretamente imagens como planos de fundo de células, você pode inserir uma imagem em uma célula e ajustar seu tamanho para cobrir a área da célula.

### Como faço para mesclar células em uma tabela?
 Você pode mesclar células usando o`CellFormat.HorizontalMerge`e`CellFormat.VerticalMerge` propriedades.