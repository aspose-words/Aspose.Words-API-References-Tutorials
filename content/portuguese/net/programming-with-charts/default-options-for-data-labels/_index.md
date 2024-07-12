---
title: Definir opções padrão para rótulos de dados em um gráfico
linktitle: Definir opções padrão para rótulos de dados em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir opções padrão para rótulos de dados em um gráfico usando Aspose.Words for .NET. Siga nosso guia passo a passo para criar e personalizar gráficos sem esforço.
type: docs
weight: 10
url: /pt/net/programming-with-charts/default-options-for-data-labels/
---
## Introdução

Ei! Você está animado para mergulhar no mundo da automação de documentos? Hoje, vamos explorar como usar Aspose.Words for .NET para criar documentos impressionantes de forma programática. Aspose.Words é uma biblioteca poderosa que permite manipular documentos do Word com facilidade e, neste tutorial, vamos nos concentrar na configuração de opções padrão para rótulos de dados em um gráfico. Quer você seja um desenvolvedor experiente ou um novato, este guia irá orientá-lo em cada etapa para que você comece a trabalhar rapidamente.

## Pré-requisitos

Antes de começarmos, vamos ter certeza de que você tem tudo o que precisa para seguir este tutorial. Aqui está uma lista de verificação rápida:

- Visual Studio ou qualquer outro IDE compatível com .NET: é aqui que você escreverá e executará seu código.
-  Aspose.Words para .NET: você pode[baixe a versão mais recente](https://releases.aspose.com/words/net/) e instale-o em seu projeto.
- Conhecimento básico de programação C#: Embora este guia seja adequado para iniciantes, um pouco de familiaridade com C# será útil.
- .NET Framework instalado: certifique-se de ter o .NET Framework configurado em sua máquina.
-  Uma licença temporária para Aspose.Words: Obtenha uma[aqui](https://purchase.aspose.com/temporary-license/) para desbloquear todas as funcionalidades.

Depois de classificar esses pré-requisitos, estamos prontos para começar!

## Importar namespaces

Primeiramente, vamos configurar nosso projeto e importar os namespaces necessários. Esses namespaces são cruciais para acessar a funcionalidade Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## Etapa 1: crie um novo documento


 A jornada começa criando um novo documento e inicializando um`DocumentBuilder` . O`DocumentBuilder` classe fornece um conjunto de métodos para manipular facilmente o conteúdo do documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crie um novo documento
Document doc = new Document();

// Inicializar DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Explicação

 Nesta etapa configuramos o documento e o construtor que utilizaremos para inserir e formatar nosso conteúdo. O`dataDir` variável contém o caminho onde salvaremos nosso documento final.

## Etapa 2: inserir um gráfico

 A seguir, adicionaremos um gráfico de pizza ao nosso documento. O`InsertChart` método do`DocumentBuilder` class torna isso super fácil.

```csharp
// Insira um gráfico de pizza
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Acesse o objeto gráfico
Chart chart = shape.Chart;
```

### Explicação

Aqui, estamos inserindo um gráfico de pizza em nosso documento. O`InsertChart` O método requer o tipo de gráfico, largura e altura como parâmetros. Após inserir o gráfico, acessamos o objeto gráfico para manipulá-lo ainda mais.

## Etapa 3: personalizar a série de gráficos

Agora, limparemos todas as séries existentes no gráfico e adicionaremos nossa série personalizada. Esta série representará nossos pontos de dados.

```csharp
// Limpar série de gráficos existentes
chart.Series.Clear();

// Adicionar nova série ao gráfico
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Explicação

Nesta etapa, garantimos que nosso gráfico esteja vazio, limpando qualquer série pré-existente. Em seguida, adicionamos uma nova série com categorias e valores personalizados, que serão exibidos em nosso gráfico de pizza.

## Etapa 4: definir opções padrão para rótulos de dados

Os rótulos de dados são cruciais para tornar seu gráfico informativo. Definiremos opções para mostrar porcentagem, valor e personalizar o separador.

```csharp
// Acesse a coleção de rótulos de dados
ChartDataLabelCollection labels = series.DataLabels;

// Definir opções de rótulo de dados
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Explicação

 Aqui, estamos acessando o`DataLabels`propriedade de nossa série para personalizar a aparência e as informações exibidas em cada rótulo de dados. Optamos por mostrar a porcentagem e o valor, ocultar as linhas de chamada e definir um separador personalizado.

## Etapa 5: salve o documento

Finalmente, salvaremos nosso documento no diretório especificado. Esta etapa garante que todas as nossas alterações sejam gravadas em um arquivo.

```csharp
// Salve o documento
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Explicação

 Nesta última etapa, salvamos nosso documento usando o`Save` método. O documento será salvo no diretório especificado por`dataDir`, com o nome "WorkingWithCharts.DefaultOptionsForDataLabels.docx".

## Conclusão

E aí está! Você criou com sucesso um documento do Word com um gráfico de pizza personalizado usando Aspose.Words for .NET. Esta poderosa biblioteca facilita a automatização da criação e manipulação de documentos, economizando tempo e esforço. Esteja você gerando relatórios, faturas ou qualquer outro tipo de documento, o Aspose.Words tem o que você precisa.

 Sinta-se à vontade para explorar[Documentação Aspose.Words](https://reference.aspose.com/words/net/) para mais recursos e exemplos. Boa codificação!

## Perguntas frequentes

### Posso usar o Aspose.Words gratuitamente?
Você pode usar Aspose.Words gratuitamente com um[licença temporária](https://purchase.aspose.com/temporary-license/) ou explore seus recursos usando o[teste grátis](https://releases.aspose.com/).

### Como obtenho suporte para Aspose.Words?
 Você pode obter suporte através do[Fórum de suporte Aspose.Words](https://forum.aspose.com/c/words/8).

### Posso adicionar outros tipos de gráficos?
 Sim, Aspose.Words oferece suporte a vários tipos de gráficos, como gráficos de barras, linhas e colunas. Verifica a[documentação](https://reference.aspose.com/words/net/) para mais detalhes.

### O Aspose.Words é compatível com o .NET Core?
 Sim, Aspose.Words é compatível com .NET Core. Você pode encontrar mais informações no[documentação](https://reference.aspose.com/words/net/).

### Como posso adquirir uma licença do Aspose.Words?
 Você pode comprar uma licença no[Aspose loja](https://purchase.aspose.com/buy).

