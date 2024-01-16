---
title: Personalizar rótulo de dados do gráfico
linktitle: Personalizar rótulo de dados do gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar e personalizar rótulos de dados em um gráfico usando Aspose.Words for .NET para fornecer informações adicionais sobre pontos de dados.
type: docs
weight: 10
url: /pt/net/programming-with-charts/chart-data-label/
---

Este tutorial explica como adicionar e personalizar rótulos de dados em um gráfico usando Aspose.Words for .NET. Os rótulos de dados fornecem informações adicionais sobre os pontos de dados em um gráfico.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um novo documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir e configurar um gráfico
 Insira um gráfico no documento usando o`InsertChart` método do`DocumentBuilder` objeto. Defina o tipo e as dimensões do gráfico desejado.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 4: personalizar rótulos de dados
Acesse a coleção de rótulos de dados da série de gráficos e modifique várias propriedades para personalizar a aparência dos rótulos de dados.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Etapa 5: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Exemplo de código-fonte para rótulo de dados do gráfico usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Por padrão, quando você adiciona rótulos de dados aos pontos de dados em um gráfico de pizza, linhas de chamada são exibidas para rótulos de dados que são
	// posicionado bem fora do final dos pontos de dados. As linhas líderes criam uma conexão visual entre um rótulo de dados e seu
	// ponto de dados correspondente.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

É isso! Você adicionou e personalizou rótulos de dados em um gráfico com sucesso usando Aspose.Words for .NET.

## Conclusão
Neste tutorial, você aprendeu como adicionar e personalizar rótulos de dados em um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo, você pode inserir um gráfico, acessar a coleção de rótulos de dados e modificar as propriedades para personalizar a aparência dos rótulos de dados. Aspose.Words for .NET fornece uma API poderosa para processamento de palavras com documentos e gráficos do Word, permitindo criar gráficos visualmente atraentes e informativos com rótulos de dados personalizados.

### Perguntas frequentes

#### Q1. O que são rótulos de dados em um gráfico?
Os rótulos de dados em um gráfico fornecem informações adicionais sobre os pontos de dados representados no gráfico. Eles podem exibir valores, categorias, nomes de séries, porcentagens ou outros detalhes relevantes dependendo do tipo e configuração do gráfico.

#### Q2. Posso personalizar a aparência dos rótulos de dados?
Sim, você pode personalizar a aparência dos rótulos de dados em um gráfico. Aspose.Words for .NET oferece opções para modificar várias propriedades de rótulos de dados, como mostrar chaves de legenda, linhas de chamada, nomes de categorias, nomes de séries, valores e muito mais. Você também pode definir separadores e formatar as etiquetas para atender às suas necessidades específicas.

#### Q3. Posso adicionar rótulos de dados a qualquer tipo de gráfico?
Sim, você pode adicionar rótulos de dados a vários tipos de gráficos, incluindo gráficos de barras, gráficos de pizza, gráficos de linhas e muito mais. O processo de adição e personalização de rótulos de dados pode variar um pouco dependendo do tipo de gráfico e da biblioteca ou ferramenta que você está usando.
