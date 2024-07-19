---
title: Formatar o número do rótulo de dados em um gráfico
linktitle: Formatar o número do rótulo de dados em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como formatar rótulos de dados em gráficos usando Aspose.Words for .NET com este guia passo a passo. Aprimore seus documentos do Word sem esforço.
type: docs
weight: 10
url: /pt/net/programming-with-charts/format-number-of-data-label/
---
## Introdução

A criação de documentos envolventes e informativos geralmente envolve a inclusão de gráficos com rótulos de dados bem formatados. Se você é um desenvolvedor .NET e deseja aprimorar seus documentos do Word com gráficos sofisticados, Aspose.Words for .NET é uma biblioteca fantástica para ajudá-lo a conseguir isso. Este tutorial irá guiá-lo através do processo de formatação de rótulos numéricos em um gráfico usando Aspose.Words for .NET, passo a passo.

## Pré-requisitos

Antes de mergulhar no código, existem alguns pré-requisitos que você precisa ter em vigor:

-  Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words for .NET instalada. Se você ainda não o instalou, você pode[baixe aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: você deve ter um ambiente de desenvolvimento .NET configurado. Visual Studio é altamente recomendado.
- Conhecimento básico de C#: Familiaridade com a programação C# é essencial, pois este tutorial envolve escrever e compreender o código C#.
-  Licença Temporária: Para usar Aspose.Words sem quaisquer limitações, você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/).

Agora, vamos mergulhar no processo passo a passo de formatação de rótulos numéricos em um gráfico.

## Importar namespaces

Primeiramente, precisamos importar os namespaces necessários para trabalhar com Aspose.Words for .NET. Adicione as seguintes linhas no topo do seu arquivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Etapa 1: configure seu diretório de documentos

Antes de começar a manipular seu documento do Word, você precisa especificar o diretório onde seu documento será salvo. Isto é essencial para a operação de salvaguarda posterior.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 2: inicializar o documento e o DocumentBuilder

 O próximo passo é inicializar um novo`Document` e um`DocumentBuilder` . O`DocumentBuilder` é uma classe auxiliar que nos permite construir o conteúdo do documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: insira um gráfico no documento

 Agora, vamos inserir um gráfico no documento usando o`DocumentBuilder`. Neste tutorial, usaremos um gráfico de linhas como exemplo.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Aqui, inserimos um gráfico de linhas com largura e altura específicas e definimos o título do gráfico.

## Etapa 4: limpar a série padrão e adicionar nova série

Por padrão, o gráfico terá algumas séries pré-geradas. Precisamos eliminá-los e adicionar nossas próprias séries com pontos de dados específicos.

```csharp
// Exclua a série gerada padrão.
chart.Series.Clear();

// Adicione novas séries com pontos de dados personalizados.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## Etapa 5: habilitar rótulos de dados

Para exibir os rótulos de dados no gráfico, precisamos habilitá-los para nossa série.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Etapa 6: formatar rótulos de dados

O núcleo deste tutorial é a formatação dos rótulos de dados. Podemos aplicar diferentes formatos numéricos a cada rótulo de dados individualmente.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Formato de moeda
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Formato de data
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Formato percentual
```

 Além disso, você pode vincular o formato de um rótulo de dados a uma célula de origem. Quando vinculado, o`NumberFormat` será redefinido para geral e herdado da célula de origem.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Etapa 7: salve o documento

Finalmente, salve o documento no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Isso salva seu documento com o nome especificado e garante que seu gráfico com rótulos de dados formatados seja preservado.

## Conclusão

formatação de rótulos de dados em um gráfico usando Aspose.Words for .NET pode melhorar muito a legibilidade e o profissionalismo de seus documentos do Word. Seguindo este guia passo a passo, agora você poderá criar um gráfico, adicionar séries de dados e formatar os rótulos de dados para atender às suas necessidades. Aspose.Words for .NET é uma ferramenta poderosa que permite ampla personalização e automação de documentos do Word, tornando-o um recurso inestimável para desenvolvedores .NET.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para criar, manipular e converter documentos do Word programaticamente usando C#.

### Posso formatar outros tipos de gráficos com Aspose.Words for .NET?
Sim, Aspose.Words for .NET oferece suporte a uma variedade de tipos de gráficos, incluindo barras, colunas, pizza e muito mais.

### Como obtenho uma licença temporária do Aspose.Words for .NET?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### É possível vincular rótulos de dados a células de origem no Excel?
Sim, você pode vincular rótulos de dados às células de origem, permitindo que o formato numérico seja herdado da célula de origem.

### Onde posso encontrar documentação mais detalhada para Aspose.Words for .NET?
 Você pode encontrar documentação abrangente[aqui](https://reference.aspose.com/words/net/).
