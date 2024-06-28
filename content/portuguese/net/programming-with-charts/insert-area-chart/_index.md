---
title: Insira gráfico de área em um documento do Word
linktitle: Insira gráfico de área em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um gráfico de área em um documento usando Aspose.Words for .NET. Adicione dados de série e salve o documento com o gráfico.
type: docs
weight: 10
url: /pt/net/programming-with-charts/insert-area-chart/
---

Este tutorial explica como usar Aspose.Words for .NET para inserir um gráfico de área em um documento. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e salvar o documento.

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

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de área no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos cinco pontos de dados com datas e valores correspondentes.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Isso completa a implementação da inserção de um gráfico de área usando Aspose.Words for .NET.

### Exemplo de código-fonte para inserir gráfico de área usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Conclusão

Neste tutorial, você aprendeu como inserir um gráfico de área em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e usando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de área, adicionar dados de série e salvar o documento com o gráfico.

Aspose.Words for .NET fornece uma API poderosa para processamento de palavras com gráficos em documentos do Word. Com apenas algumas linhas de código, você pode criar gráficos de área com aparência profissional e personalizá-los de acordo com suas necessidades. Os gráficos de área são comumente usados para exibir a magnitude e as tendências dos dados ao longo do tempo ou categorias.

Ao utilizar o Aspose.Words for .NET, você pode automatizar o processo de geração de documentos com gráficos de área, economizando tempo e esforço na criação manual de documentos. A biblioteca oferece uma ampla variedade de tipos de gráficos e opções de personalização, permitindo criar gráficos visualmente atraentes e informativos em seus documentos do Word.

### Perguntas frequentes

#### Q1. O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma poderosa biblioteca de processamento de documentos que permite aos desenvolvedores criar, modificar e converter documentos do Word programaticamente em aplicativos .NET. Ele fornece um conjunto abrangente de APIs para processamento de palavras com elementos de documentos, incluindo gráficos, parágrafos, tabelas e muito mais.

#### Q2. Como instalo o Aspose.Words para .NET?
Para instalar o Aspose.Words for .NET, você pode usar o gerenciador de pacotes NuGet no Visual Studio para instalar a biblioteca diretamente em seu projeto. Basta pesquisar “Apose.Words” no gerenciador de pacotes NuGet e instalar o pacote.

#### Q3. Posso personalizar a aparência do gráfico de área?
Sim, usando Aspose.Words for .NET, você pode personalizar vários aspectos da aparência do gráfico de área. Você pode modificar propriedades como título do gráfico, cor da série, rótulos dos eixos e formatação da área do gráfico. A biblioteca fornece um rico conjunto de APIs para controlar os elementos visuais do gráfico e criar uma aparência personalizada que atenda às suas necessidades.

#### Q4. Posso adicionar várias séries ao gráfico de área?
Sim, você pode adicionar várias séries ao gráfico de área usando Aspose.Words for .NET. Cada série representa um conjunto de pontos de dados plotados no gráfico. Você pode adicionar séries com diferentes conjuntos de dados e personalizar cada série individualmente, incluindo nome, pontos de dados e aparência.

#### Q5. Posso salvar o documento com o gráfico de área inserido em diferentes formatos?
 Sim, Aspose.Words for .NET permite salvar o documento com o gráfico de área inserido em vários formatos, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato de saída desejado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento. O gráfico de área inserido será preservado no documento salvo.

#### Q6. Posso modificar os dados e a aparência do gráfico de área após inseri-lo?
Sim, após inserir o gráfico de área no documento, você pode modificar seus dados e aparência utilizando as APIs fornecidas pelo Aspose.Words for .NET. Você pode atualizar os dados da série, alterar o tipo de gráfico, personalizar as propriedades dos eixos e aplicar opções de formatação para criar gráficos dinâmicos e interativos em seus documentos do Word.