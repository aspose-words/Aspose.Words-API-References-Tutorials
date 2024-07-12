---
title: Personalize um único ponto de dados do gráfico em um gráfico
linktitle: Personalize um único ponto de dados do gráfico em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como personalizar pontos de dados de gráfico únicos usando Aspose.Words for .NET em um guia passo a passo detalhado. Aprimore seus gráficos com marcadores e tamanhos exclusivos.
type: docs
weight: 10
url: /pt/net/programming-with-charts/single-chart-data-point/
---
## Introdução

Já se perguntou como você pode fazer seus gráficos aparecerem com pontos de dados exclusivos? Bem, hoje é seu dia de sorte! Estamos mergulhando na personalização de um único ponto de dados do gráfico usando Aspose.Words for .NET. Aperte o cinto para um tutorial passo a passo que não é apenas informativo, mas também divertido e fácil de seguir.

## Pré-requisitos

Antes de começarmos, vamos garantir que você tenha todos os itens essenciais em vigor:

-  Biblioteca Aspose.Words for .NET: Certifique-se de ter a versão mais recente.[Baixe aqui](https://releases.aspose.com/words/net/).
- .NET Framework: certifique-se de ter o .NET Framework instalado em sua máquina.
- Compreensão básica de C#: Uma compreensão básica de programação C# será útil.
- Ambiente de Desenvolvimento Integrado (IDE): Visual Studio é recomendado.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários para dar o pontapé inicial:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Etapa 1: inicializar o documento e o DocumentBuilder

Tudo bem, vamos começar inicializando um novo documento e um DocumentBuilder. Esta será a tela do nosso gráfico.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aqui,`dataDir` é o caminho do diretório onde você salvará seu documento. O`DocumentBuilder` classe ajuda na construção do documento.

## Etapa 2: inserir um gráfico

A seguir, vamos inserir um gráfico de linhas no documento. Este será o nosso playground para personalizar pontos de dados.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

 O`InsertChart` O método usa o tipo de gráfico, largura e altura como parâmetros. Neste caso, estamos inserindo um gráfico de linhas com largura de 432 e altura de 252.

## Etapa 3: acessar a série de gráficos

Agora é hora de acessar a série dentro do nosso gráfico. Um gráfico pode ter várias séries e cada série contém pontos de dados.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];
```

Aqui, estamos acessando as duas primeiras séries do nosso gráfico. 

## Etapa 4: personalizar pontos de dados

É aqui que a mágica acontece! Vamos personalizar pontos de dados específicos em nossa série.

```csharp
ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];
```

Estamos buscando os pontos de dados da primeira série. Agora, vamos personalizar esses pontos.

### Personalizar ponto de dados 00

```csharp
dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;
```

 Para`dataPoint00`, estamos definindo uma explosão (útil para gráficos de pizza), alterando o símbolo do marcador para um círculo e definindo o tamanho do marcador como 15.

### Personalizar ponto de dados 01

```csharp
dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;
```

 Para`dataPoint01`, estamos alterando o símbolo do marcador para um diamante e definindo o tamanho do marcador como 20.

### Personalize o ponto de dados na série 1

```csharp
ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

 Para o terceiro ponto de dados em`series1`, estamos configurando-o para inverter se o valor for negativo, alterando o símbolo do marcador para uma estrela e definindo o tamanho do marcador para 20.

## Etapa 5: salve o documento

Por fim, vamos salvar nosso documento com todas as customizações.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

 Esta linha salva o documento no diretório especificado com o nome`WorkingWithCharts.SingleChartDataPoint.docx`.

## Conclusão

aí está! Você personalizou com sucesso pontos de dados individuais em um gráfico usando Aspose.Words for .NET. Ajustando algumas propriedades, você pode tornar seus gráficos muito mais informativos e visualmente atraentes. Então, vá em frente e experimente diferentes marcadores e tamanhos para ver o que funciona melhor para seus dados.

## Perguntas frequentes

### Posso personalizar pontos de dados em outros tipos de gráficos?

Absolutamente! Você pode personalizar pontos de dados em vários tipos de gráficos, incluindo gráficos de barras, gráficos de pizza e muito mais. O processo é semelhante em diferentes tipos de gráfico.

### É possível adicionar rótulos personalizados aos pontos de dados?

 Sim, você pode adicionar rótulos personalizados a pontos de dados usando o`ChartDataPoint.Label` propriedade. Isso permite fornecer mais contexto para cada ponto de dados.

### Como posso remover um ponto de dados de uma série?

 Você pode remover um ponto de dados definindo sua visibilidade como falsa usando`dataPoint.IsVisible = false`.

### Posso usar imagens como marcadores para pontos de dados?

Embora Aspose.Words não suporte o uso de imagens diretamente como marcadores, você pode criar formas personalizadas e usá-las como marcadores.

### É possível animar pontos de dados no gráfico?

Aspose.Words for .NET não oferece suporte a animação para pontos de dados do gráfico. No entanto, você pode criar gráficos animados usando outras ferramentas e incorporá-los aos seus documentos do Word.