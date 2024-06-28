---
title: Insira gráfico de dispersão em documento do Word
linktitle: Insira gráfico de dispersão em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um gráfico de dispersão em um documento usando Aspose.Words for .NET. Adicione dados de série com coordenadas X e Y.
type: docs
weight: 10
url: /pt/net/programming-with-charts/insert-scatter-chart/
---

Este tutorial explica como usar Aspose.Words for .NET para inserir um gráfico de dispersão em um documento. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e salvar o documento.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

- Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo usando o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório do documento onde o documento de saída será salvo.

## Passo 2: Crie um novo documento e insira um gráfico.

 Crie um novo`Document` objeto e um`DocumentBuilder` para construir o documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de dispersão no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos dois conjuntos de coordenadas X e Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Isso conclui a implementação da inserção de um gráfico de dispersão usando Aspose.Words for .NET.

### Exemplo de código-fonte para inserir gráfico de dispersão usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusão

Neste tutorial, você aprendeu como inserir um gráfico de dispersão em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e usando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de dispersão, adicionar dados de série com coordenadas X e Y e salvar o documento com o gráfico.

Aspose.Words for .NET fornece uma API abrangente para processamento de palavras com gráficos em documentos do Word. Os gráficos de dispersão são úteis para visualizar e analisar dados com duas variáveis numéricas. Com Aspose.Words for .NET, você pode criar facilmente gráficos de dispersão que representam a relação entre os valores X e Y e identificar padrões ou tendências nos dados.

Ao usar o Aspose.Words for .NET, você pode automatizar o processo de geração de documentos com gráficos de dispersão, economizando tempo e esforço na criação manual de documentos. A biblioteca oferece uma ampla variedade de tipos de gráficos, incluindo gráficos de dispersão, e oferece várias opções de personalização para adaptar a aparência do gráfico de acordo com suas necessidades.

### Perguntas frequentes

#### Q1. O que é um gráfico de dispersão?
Um gráfico de dispersão é um tipo de gráfico que exibe a relação entre duas variáveis numéricas. Consiste em uma série de pontos plotados em uma grade de coordenadas, com uma variável representada no eixo X e a outra variável representada no eixo Y. Os gráficos de dispersão são usados para identificar padrões, correlações ou tendências entre dois conjuntos de pontos de dados.

#### Q2. Posso adicionar várias séries ao gráfico de dispersão?
Sim, você pode adicionar várias séries ao gráfico de dispersão usando Aspose.Words for .NET. Cada série representa um conjunto de pontos de dados com suas respectivas coordenadas X e Y. Ao adicionar várias séries, você pode comparar e analisar diferentes conjuntos de dados no mesmo gráfico de dispersão, fornecendo uma visão abrangente dos seus dados.

#### Q3. Posso personalizar a aparência do gráfico de dispersão?
Sim, usando Aspose.Words for .NET, você pode personalizar vários aspectos da aparência do gráfico de dispersão. Você pode modificar propriedades como cor da série, formato do marcador, rótulos dos eixos e formatação da área do gráfico. A biblioteca fornece um rico conjunto de APIs para controlar os elementos visuais do gráfico e criar uma aparência personalizada que atenda às suas necessidades.

#### Q4. Posso salvar o documento com o gráfico de dispersão inserido em diferentes formatos?
Sim, Aspose.Words for .NET permite salvar o documento com o gráfico de dispersão inserido em vários formatos, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato de saída desejado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento. O gráfico de dispersão inserido será preservado no documento salvo.

#### Q5. Posso modificar os dados e a aparência do gráfico de dispersão após inseri-lo?
Sim, após inserir o gráfico de dispersão no documento, você pode modificar seus dados e aparência usando as APIs fornecidas pelo Aspose.Words for .NET. Você pode atualizar os dados da série com novas coordenadas X e Y, alterar as formas e cores dos marcadores, personalizar as propriedades dos eixos e aplicar opções de formatação para criar gráficos dinâmicos e interativos em seus documentos do Word.