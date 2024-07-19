---
title: Limites do eixo em um gráfico
linktitle: Limites do eixo em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir os limites de um eixo em um gráfico usando Aspose.Words for .NET controlando o intervalo de valores exibidos no eixo.
type: docs
weight: 10
url: /pt/net/programming-with-charts/bounds-of-axis/
---
## Introdução

Você deseja criar documentos profissionais com gráficos em .NET? Você está no lugar certo! Este guia orientará você no processo de uso do Aspose.Words for .NET para definir os limites do eixo em um gráfico. Descreveremos cada etapa para garantir que você possa acompanhar facilmente, mesmo se for novo na biblioteca. Então, vamos mergulhar e começar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Aspose.Words para .NET: você pode[download](https://releases.aspose.com/words/net/) a versão mais recente ou use um[teste grátis](https://releases.aspose.com/).
- .NET Framework: certifique-se de ter o .NET instalado em seu sistema.
- IDE: Um ambiente de desenvolvimento como o Visual Studio.

Depois de ter tudo pronto, podemos passar para as próximas etapas.

## Importar namespaces

Para começar, você precisará importar os namespaces necessários. Isso permitirá que você acesse a biblioteca Aspose.Words e seus recursos de gráficos.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Etapa 1: configure seu diretório de documentos

Primeiramente, você precisa configurar o diretório onde seu documento será salvo. Este é um passo simples, mas crucial para organizar seus arquivos.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um novo documento

A seguir, crie um novo objeto de documento. Este documento servirá como contêiner para seu gráfico.

```csharp
Document doc = new Document();
```

## Etapa 3: inicializar o Document Builder

A classe DocumentBuilder fornece uma maneira rápida e fácil de criar documentos. Inicialize-o com seu documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 4: inserir um gráfico

Agora é hora de inserir um gráfico em seu documento. Neste exemplo, usaremos um gráfico de colunas.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 5: limpar séries existentes

Para garantir que você comece do zero, limpe todas as séries existentes do gráfico.

```csharp
chart.Series.Clear();
```

## Etapa 6: adicionar dados ao gráfico

Aqui, adicionamos dados ao gráfico. Isso inclui a especificação do nome da série e dos pontos de dados.

```csharp
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Etapa 7: definir limites do eixo

Definir os limites para o eixo Y garante que seu gráfico seja dimensionado corretamente.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Etapa 8: salve o documento

Finalmente, salve seu documento no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

é isso! Você criou com sucesso um documento com um gráfico usando Aspose.Words for .NET. 

## Conclusão

Usando Aspose.Words for .NET, você pode criar e manipular facilmente gráficos em seus documentos. Este guia passo a passo mostrou como definir os limites do eixo em um gráfico, tornando a apresentação de seus dados mais precisa e profissional. Esteja você gerando relatórios, apresentações ou qualquer outro documento, Aspose.Words fornece as ferramentas que você precisa.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca que permite criar, modificar e converter documentos do Word programaticamente usando o .NET framework.

### Como configuro o Aspose.Words para .NET?
 Você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/) e siga as instruções de instalação fornecidas.

### Posso usar o Aspose.Words gratuitamente?
 Sim, você pode usar um[teste grátis](https://releases.aspose.com/) ou obter um[licença temporária](https://purchase.aspose.com/temporary-license/).

### Onde posso encontrar documentação para Aspose.Words for .NET?
 Documentação detalhada está disponível[aqui](https://reference.aspose.com/words/net/).

### Como posso obter suporte para Aspose.Words?
 Você pode visitar o[Fórum de suporte](https://forum.aspose.com/c/words/8) para assistência.