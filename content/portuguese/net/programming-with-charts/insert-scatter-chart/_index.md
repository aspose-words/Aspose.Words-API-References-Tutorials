---
title: Insira gráfico de dispersão em documento do Word
linktitle: Insira gráfico de dispersão em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um gráfico de dispersão no Word com Aspose.Words for .NET. Etapas fáceis para integrar representações visuais de dados em seus documentos.
type: docs
weight: 10
url: /pt/net/programming-with-charts/insert-scatter-chart/
---
## Introdução

Neste tutorial, você aprenderá como aproveitar o Aspose.Words for .NET para inserir um gráfico de dispersão em seu documento do Word. Os gráficos de dispersão são ferramentas visuais poderosas que podem exibir pontos de dados com eficácia com base em duas variáveis, tornando seus documentos mais envolventes e informativos.

## Pré-requisitos

Antes de mergulharmos na criação de gráficos de dispersão com Aspose.Words for .NET, certifique-se de ter os seguintes pré-requisitos:

1.  Instalação do Aspose.Words for .NET: Baixe e instale o Aspose.Words for .NET em[aqui](https://releases.aspose.com/words/net/).
   
2. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# e o framework .NET será benéfica.

## Importar namespaces

Para começar, você precisa importar os namespaces necessários em seu projeto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
```

Agora, vamos detalhar o processo de inserção de um gráfico de dispersão em seu documento do Word usando Aspose.Words for .NET:

## Etapa 1: inicializar o documento e o DocumentBuilder

 Primeiro, inicialize uma nova instância do`Document` classe e`DocumentBuilder` class para começar a construir seu documento.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: insira o gráfico de dispersão

 Use o`InsertChart` método do`DocumentBuilder` class para inserir um gráfico de dispersão no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar séries de dados ao gráfico

Agora, adicione séries de dados ao seu gráfico de dispersão. Este exemplo demonstra a adição de uma série com pontos de dados específicos.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Etapa 4: salve o documento

 Por fim, salve o documento modificado no local desejado usando o`Save` método do`Document` aula.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusão

Parabéns! Você aprendeu com sucesso como inserir um gráfico de dispersão em seu documento do Word usando Aspose.Words for .NET. Os gráficos de dispersão são excelentes ferramentas para visualizar relacionamentos de dados e, com Aspose.Words, você pode integrá-los facilmente aos seus documentos para aumentar a clareza e a compreensão.

## Perguntas frequentes

### Posso personalizar a aparência do gráfico de dispersão usando Aspose.Words?
Sim, Aspose.Words permite ampla personalização de propriedades do gráfico, como cores, eixos e rótulos.

### O Aspose.Words é compatível com diferentes versões do Microsoft Word?
Aspose.Words oferece suporte a várias versões do Microsoft Word, garantindo compatibilidade entre plataformas.

### O Aspose.Words oferece suporte para outros tipos de gráficos?
Sim, Aspose.Words oferece suporte a uma ampla variedade de tipos de gráficos, incluindo gráficos de barras, gráficos de linhas e gráficos de pizza.

### Posso atualizar dinamicamente os dados no gráfico de dispersão de forma programática?
Com certeza, você pode atualizar os dados do gráfico dinamicamente usando chamadas de API Aspose.Words.

### Onde posso obter mais assistência ou suporte para Aspose.Words?
 Para obter mais assistência, visite o[Fórum de suporte Aspose.Words](https://forum.aspose.com/c/words/8).