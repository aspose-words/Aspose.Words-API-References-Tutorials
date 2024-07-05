---
title: Unidade de intervalo entre rótulos no eixo de um gráfico
linktitle: Unidade de intervalo entre rótulos no eixo de um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir a unidade de intervalo entre rótulos no eixo de um gráfico usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Este tutorial explica como usar Aspose.Words for .NET para definir a unidade de intervalo entre os rótulos no eixo de um gráfico. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e personalizar os rótulos dos eixos.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

- Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo usando o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório do documento onde o documento de saída será salvo.

## Passo 2: Crie um novo documento e insira um gráfico

 Crie um novo`Document` objeto e um`DocumentBuilder` para construir o documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de colunas no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos cinco itens com seus valores correspondentes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Etapa 4: personalizar os rótulos dos eixos

 Para definir a unidade de intervalo entre rótulos no eixo X, acesse o`AxisX` propriedade do gráfico e defina o`TickLabelSpacing` propriedade para o valor desejado. Neste exemplo, definimos o espaçamento como 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Etapa 5: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Isso completa a implementação da configuração da unidade de intervalo entre os rótulos no eixo usando Aspose.Words for .NET.

### Exemplo de código-fonte para unidade de intervalo entre rótulos no eixo usando Aspose.Words para .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Conclusão

Neste tutorial, você aprendeu como definir a unidade de intervalo entre os rótulos no eixo de um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de colunas, adicionar dados de série e personalizar os rótulos dos eixos para controlar o espaçamento entre os rótulos.

Aspose.Words for .NET fornece recursos poderosos para manipular gráficos em documentos do Word. Ao definir a unidade de intervalo entre os rótulos no eixo, você pode controlar a densidade de exibição dos rótulos e melhorar a legibilidade dos seus gráficos. Isso permite otimizar a apresentação dos dados e melhorar a experiência geral do usuário.

Com Aspose.Words for .NET, você tem a flexibilidade de personalizar vários aspectos do gráfico, incluindo os rótulos dos eixos. Você pode definir a unidade de intervalo desejada para garantir que os rótulos tenham espaçamento adequado e forneçam uma representação clara dos pontos de dados.

### Perguntas frequentes

#### Q1. O que são rótulos de eixo em um gráfico?
Os rótulos dos eixos em um gráfico referem-se à representação textual de valores ao longo do eixo horizontal (eixo X) ou vertical (eixo Y) do gráfico. Esses rótulos ajudam a identificar e interpretar os pontos de dados plotados no gráfico. Os rótulos dos eixos fornecem contexto e permitem que os usuários entendam a escala e o intervalo de valores no gráfico.

#### Q2. Como posso personalizar o espaçamento entre os rótulos dos eixos?
 Para personalizar o espaçamento entre os rótulos dos eixos em um gráfico usando Aspose.Words for .NET, você pode acessar o`AxisX` ou`AxisY` propriedade do gráfico e modificar o`TickLabelSpacing` propriedade. Ao definir o`TickLabelSpacing` para um valor específico, você pode controlar a unidade de intervalo entre as etiquetas no respectivo eixo, ajustando o espaçamento de acordo com sua necessidade.

#### Q3. Posso definir espaçamentos diferentes para os rótulos dos eixos X e Y?
Sim, você pode definir espaçamentos diferentes para os rótulos do eixo X e do eixo Y usando Aspose.Words for .NET. Acesse o respectivo eixo (`AxisX` para eixo X ou`AxisY` para o eixo Y) do gráfico e modifique o`TickLabelSpacing`propriedade individualmente para cada eixo. Isso permite que você tenha diferentes unidades de intervalo e espaçamento para os rótulos nos eixos X e Y, proporcionando controle refinado sobre a aparência do gráfico.

#### Q4. Qual é o significado da unidade de intervalo entre os rótulos no eixo?
A unidade de intervalo entre os rótulos no eixo determina o espaçamento entre os rótulos consecutivos exibidos no gráfico. Ao definir a unidade de intervalo, você pode controlar a densidade das etiquetas e garantir que elas estejam espaçadas adequadamente para evitar superlotação e sobreposição. Ajustar a unidade de intervalo permite apresentar os dados de uma forma mais legível e visualmente atraente.

#### Q5. Posso modificar outras propriedades dos rótulos dos eixos?
Sim, Aspose.Words for .NET fornece uma ampla gama de propriedades para personalizar a aparência e o comportamento dos rótulos dos eixos. Você pode modificar propriedades como fonte, tamanho, cor, orientação, alinhamento e muito mais para obter a formatação e o estilo desejados para os rótulos dos eixos. A biblioteca oferece amplo controle sobre os elementos do gráfico, permitindo criar gráficos com aparência profissional adaptados às suas necessidades específicas.