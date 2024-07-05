---
title: Insira gráfico de colunas em um documento do Word
linktitle: Insira gráfico de colunas em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um gráfico de colunas em um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/insert-column-chart/
---

Este tutorial explica como usar Aspose.Words for .NET para inserir um gráfico de colunas em um documento. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e salvar o documento.

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

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos duas categorias e seus valores correspondentes.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Isso conclui a implementação da inserção de um gráfico de colunas usando Aspose.Words for .NET.

### Exemplo de código-fonte para inserir gráfico de colunas usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Conclusão

Neste tutorial, você aprendeu como inserir um gráfico de colunas em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e usando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de colunas, adicionar dados de série e salvar o documento com o gráfico.

Aspose.Words for .NET fornece uma API poderosa para processamento de palavras com gráficos em documentos do Word. Os gráficos de colunas são comumente usados para exibir e comparar dados em diferentes categorias ou grupos. Com Aspose.Words for .NET, você pode criar facilmente gráficos de colunas que visualizam seus dados de maneira eficaz e fornecem insights valiosos.

Ao usar o Aspose.Words for .NET, você pode automatizar o processo de geração de documentos com gráficos de colunas, economizando tempo e esforço na criação manual de documentos. A biblioteca oferece uma ampla variedade de tipos de gráficos e opções de personalização, permitindo criar gráficos visualmente atraentes e ricos em dados em seus documentos do Word.

### Perguntas frequentes

#### Q1. O que é um gráfico de colunas?
Um gráfico de colunas é um tipo de gráfico que representa dados em barras ou colunas verticais. Cada coluna normalmente representa uma categoria ou grupo, e a altura ou comprimento da coluna indica o valor dos dados associados a essa categoria. Os gráficos de colunas são comumente usados para comparar dados em diferentes categorias ou para rastrear alterações ao longo do tempo.

#### Q2. Posso adicionar várias séries ao gráfico de colunas?
Sim, você pode adicionar várias séries ao gráfico de colunas usando Aspose.Words for .NET. Cada série representa um conjunto de pontos de dados com suas respectivas categorias e valores. Ao adicionar várias séries, você pode comparar e analisar diferentes conjuntos de dados no mesmo gráfico, fornecendo uma visão abrangente dos seus dados.

#### Q3. Posso personalizar a aparência do gráfico de colunas?
Sim, usando Aspose.Words for .NET, você pode personalizar vários aspectos da aparência do gráfico de colunas. Você pode modificar propriedades como cor da série, rótulos dos eixos, largura da coluna e formatação da área do gráfico. A biblioteca fornece um rico conjunto de APIs para controlar os elementos visuais do gráfico e criar uma aparência personalizada que atenda às suas necessidades.

#### Q4. Posso salvar o documento com o gráfico de colunas inserido em diferentes formatos?
 Sim, Aspose.Words for .NET permite salvar o documento com o gráfico de colunas inserido em vários formatos, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato de saída desejado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento. O gráfico de colunas inserido será preservado no documento salvo.

#### Q5. Posso modificar os dados e a aparência do gráfico de colunas após inseri-lo?
Sim, após inserir o gráfico de colunas no documento, você pode modificar seus dados e aparência utilizando as APIs fornecidas pelo Aspose.Words for .NET. Você pode atualizar os dados da série, alterar as cores das colunas, personalizar as propriedades dos eixos e aplicar opções de formatação para criar gráficos dinâmicos e interativos em seus documentos do Word.