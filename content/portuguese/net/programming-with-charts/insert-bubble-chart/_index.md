---
title: Insira gráfico de bolhas em documento do Word
linktitle: Insira gráfico de bolhas em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um gráfico de bolhas em um documento usando Aspose.Words for .NET. Adicione dados de série com valores X, Y e tamanho de bolha.
type: docs
weight: 10
url: /pt/net/programming-with-charts/insert-bubble-chart/
---

Este tutorial explica como usar Aspose.Words for .NET para inserir um gráfico de bolhas em um documento. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e salvar o documento.

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

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de bolhas no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos três pontos de dados com valores correspondentes de X, Y e tamanho de bolha.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Isso conclui a implementação da inserção de um gráfico de bolhas usando Aspose.Words for .NET.

### Exemplo de código-fonte para inserir gráfico de bolhas usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Conclusão

Neste tutorial, você aprendeu como inserir um gráfico de bolhas em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e usando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de bolhas, adicionar dados de série e salvar o documento com o gráfico.

Aspose.Words for .NET fornece uma API poderosa para processamento de palavras com gráficos em documentos do Word. Os gráficos de bolhas são ideais para visualizar dados tridimensionais, onde cada ponto de dados é representado por uma bolha com coordenadas X e Y e um valor de tamanho. Com Aspose.Words for .NET, você pode criar gráficos de bolhas dinâmicos e informativos que aprimoram a representação visual de seus dados.

Ao usar o Aspose.Words for .NET, você pode automatizar o processo de geração de documentos com gráficos de bolhas, economizando tempo e esforço na criação manual de documentos. A biblioteca oferece uma ampla variedade de tipos de gráficos e opções de personalização, permitindo criar gráficos visualmente atraentes e ricos em dados em seus documentos do Word.

### Perguntas frequentes

#### Q1. O que é um gráfico de bolhas?
Um gráfico de bolhas é um tipo de gráfico que exibe dados tridimensionais usando bolhas ou esferas. Cada ponto de dados é representado por uma bolha, onde as coordenadas X e Y determinam a posição da bolha no gráfico e o tamanho da bolha representa a terceira dimensão dos dados. Os gráficos de bolhas são úteis para visualizar relacionamentos e padrões entre múltiplas variáveis.

#### Q2. Posso adicionar várias séries ao gráfico de bolhas?
Sim, você pode adicionar várias séries ao gráfico de bolhas usando Aspose.Words for .NET. Cada série representa um conjunto de pontos de dados com seus respectivos valores de X, Y e tamanho de bolha. Ao adicionar várias séries, você pode comparar e analisar diferentes conjuntos de dados no mesmo gráfico, fornecendo uma visão abrangente dos seus dados.

#### Q3. Posso personalizar a aparência do gráfico de bolhas?
Sim, usando Aspose.Words for .NET, você pode personalizar vários aspectos da aparência do gráfico de bolhas. Você pode modificar propriedades como cor da série, tamanho da bolha, rótulos dos eixos e formatação da área do gráfico. A biblioteca fornece um rico conjunto de APIs para controlar os elementos visuais do gráfico e criar uma aparência personalizada que atenda às suas necessidades.

#### Q4. Posso salvar o documento com o gráfico de bolhas inserido em diferentes formatos?
 Sim, Aspose.Words for .NET permite salvar o documento com o gráfico de bolhas inserido em vários formatos, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato de saída desejado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento. O gráfico de bolhas inserido será preservado no documento salvo.

#### Q5. Posso modificar os dados e a aparência do gráfico de bolhas após inseri-lo?
Sim, após inserir o gráfico de bolhas no documento, você pode modificar seus dados e aparência usando as APIs fornecidas pelo Aspose.Words for .NET. Você pode atualizar os dados da série, alterar o tamanho da bolha, personalizar as propriedades dos eixos e aplicar opções de formatação para criar gráficos dinâmicos e interativos em seus documentos do Word.