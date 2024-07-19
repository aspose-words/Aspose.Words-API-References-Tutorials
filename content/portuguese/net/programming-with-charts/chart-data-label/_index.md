---
title: Personalizar rótulo de dados do gráfico
linktitle: Personalizar rótulo de dados do gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como personalizar rótulos de dados de gráficos usando Aspose.Words for .NET em um guia passo a passo. Perfeito para desenvolvedores .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/chart-data-label/
---
## Introdução

Você deseja aprimorar seus aplicativos .NET com recursos de processamento de documentos dinâmicos e personalizados? Aspose.Words for .NET pode ser apenas a sua resposta! Neste guia, nos aprofundaremos na personalização de rótulos de dados de gráficos usando Aspose.Words for .NET, uma biblioteca poderosa para criar, modificar e converter documentos do Word. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este tutorial irá orientá-lo em cada etapa, garantindo que você entenda como utilizar essa ferramenta de maneira eficaz.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1. Visual Studio: instale o Visual Studio 2019 ou posterior.
2. .NET Framework: certifique-se de ter o .NET Framework 4.0 ou posterior.
3.  Aspose.Words for .NET: Baixe e instale Aspose.Words for .NET do[Link para Download](https://releases.aspose.com/words/net/).
4. Conhecimento básico de C#: Familiaridade com programação C# é essencial.
5.  Uma licença válida: obtenha uma[licença temporária](https://purchase.aspose.com/temporary-license/) ou compre um no[comprar link](https://purchase.aspose.com/buy).

## Importar namespaces

Para começar, você precisa importar os namespaces necessários para o seu projeto C#. Esta etapa é crucial porque garante que você tenha acesso a todas as classes e métodos fornecidos pelo Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Charts;
```

## Etapa 1: inicializar o documento e o DocumentBuilder

Para criar e manipular documentos do Word, primeiro precisamos inicializar uma instância do`Document` aula e um`DocumentBuilder` objeto.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Explicação

- Documento doc: Cria uma nova instância da classe Document.
- Construtor DocumentBuilder: O DocumentBuilder ajuda na inserção de conteúdo no objeto Document.

## Etapa 2: inserir um gráfico

 A seguir, inseriremos um gráfico de barras no documento usando o`DocumentBuilder` objeto.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

### Explicação

- Forma da forma: representa o gráfico como uma forma no documento.
- builder.InsertChart(ChartType.Bar, 432, 252): Insere um gráfico de barras com dimensões especificadas.

## Etapa 3: acesse a série de gráficos

Para personalizar os rótulos dos dados, primeiro precisamos acessar as séries do gráfico.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
```

### Explicação

- ChartSeries series0: recupera a primeira série do gráfico, que iremos personalizar.

## Etapa 4: personalizar rótulos de dados

Os rótulos de dados podem ser personalizados para exibir diversas informações. Configuraremos os rótulos para mostrar a chave da legenda, o nome da série e o valor, enquanto ocultaremos o nome da categoria e a porcentagem.

```csharp
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

### Explicação

- Rótulos ChartDataLabelCollection: acessa os rótulos de dados da série.
- rótulos.ShowLegendKey: Exibe a chave da legenda.
- rótulos.ShowLeaderLines: mostra linhas líderes para rótulos de dados posicionados fora dos pontos de dados.
- rótulos.ShowCategoryName: oculta o nome da categoria.
- rótulos.ShowPercentage: oculta o valor percentual.
- rótulos.ShowSeriesName: Exibe o nome da série.
- rótulos.ShowValue: Exibe o valor dos pontos de dados.
- rótulos.Separador: Define o separador para os rótulos de dados.

## Etapa 5: salve o documento

Finalmente, salve o documento no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Explicação

- doc.Save: salva o documento com o nome especificado no diretório fornecido.

## Conclusão

 Parabéns! Você personalizou com sucesso rótulos de dados de gráfico usando Aspose.Words for .NET. Esta biblioteca oferece uma solução robusta para lidar com documentos Word de forma programática, tornando mais fácil para os desenvolvedores criar aplicativos sofisticados e dinâmicos de processamento de documentos. Mergulhe no[documentação](https://reference.aspose.com/words/net/) para explorar mais recursos e capacidades.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma poderosa biblioteca de processamento de documentos que permite aos desenvolvedores criar, modificar e converter documentos do Word programaticamente.

### Como instalo o Aspose.Words para .NET?
 Você pode baixá-lo e instalá-lo no[Link para Download](https://releases.aspose.com/words/net/). Siga as instruções de instalação fornecidas.

### Posso experimentar o Aspose.Words for .NET gratuitamente?
 Sim, você pode obter um[teste grátis](https://releases.aspose.com/) ou um[licença temporária](https://purchase.aspose.com/temporary-license/)para avaliar o produto.

### O Aspose.Words for .NET é compatível com o .NET Core?
Sim, Aspose.Words for .NET é compatível com .NET Core, .NET Standard e .NET Framework.

### Onde posso obter suporte para Aspose.Words for .NET?
 Você pode visitar o[Fórum de suporte](https://forum.aspose.com/c/words/8) para obter ajuda e assistência da comunidade e especialistas Aspose.
