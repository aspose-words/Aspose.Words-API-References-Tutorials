---
title: Configurações de largura preferidas
linktitle: Configurações de largura preferidas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar tabelas com configurações de largura absoluta, relativa e automática no Aspose.Words for .NET com este guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-tables/preferred-width-settings/
---
## Introdução

As tabelas são uma forma poderosa de organizar e apresentar informações em seus documentos do Word. Ao trabalhar com tabelas no Aspose.Words for .NET, você tem várias opções para definir a largura das células da tabela para garantir que elas se ajustem perfeitamente ao layout do seu documento. Este guia orientará você no processo de criação de tabelas com configurações de largura preferidas usando Aspose.Words for .NET, com foco nas opções de dimensionamento absoluto, relativo e automático. 

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter o seguinte:

1.  Aspose.Words for .NET: Certifique-se de ter o Aspose.Words for .NET instalado em seu ambiente de desenvolvimento. Você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).

2. Ambiente de desenvolvimento .NET: configure um ambiente de desenvolvimento .NET, como o Visual Studio.

3. Conhecimento básico de C#: A familiaridade com a programação C# ajudará você a entender melhor os trechos de código e exemplos.

4.  Documentação Aspose.Words: Consulte o[Documentação Aspose.Words](https://reference.aspose.com/words/net/) para obter informações detalhadas sobre a API e leitura adicional.

## Importar namespaces

Antes de começar a codificar, você precisa importar os namespaces necessários para seu projeto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Esses namespaces fornecem acesso às funcionalidades principais do Aspose.Words e do objeto Table, permitindo manipular tabelas de documentos.

Vamos dividir o processo de criação de uma tabela com diferentes configurações de largura preferidas em etapas claras e gerenciáveis.

## Etapa 1: inicializar o documento e o DocumentBuilder

Título: Criando um Novo Documento e DocumentBuilder

 Explicação: Comece criando um novo documento do Word e um`DocumentBuilder` instância. O`DocumentBuilder` class fornece uma maneira simples de adicionar conteúdo ao seu documento.

```csharp
// Defina o caminho para salvar o documento.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crie um novo documento.
Document doc = new Document();

// Crie um DocumentBuilder para este documento.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aqui, você especifica o diretório onde o documento será salvo e inicializa o`Document`e`DocumentBuilder` objetos.

## Etapa 2: insira a primeira célula da tabela com largura absoluta

Insira a primeira célula na tabela com largura fixa de 40 pontos. Isso garantirá que esta célula sempre mantenha uma largura de 40 pontos, independentemente do tamanho da tabela.

```csharp

// Insira uma célula de tamanho absoluto.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

Nesta etapa, você começa a criar a tabela e insere uma célula com largura absoluta. O`PreferredWidth.FromPoints(40)` método define a largura da célula para 40 pontos, e`Shading.BackgroundPatternColor` aplica uma cor de fundo amarelo claro.

## Etapa 3: inserir uma célula de tamanho relativo

Insira outra célula com largura igual a 20% da largura total da tabela. Esse dimensionamento relativo garante que a célula se ajuste proporcionalmente à largura da tabela.

```csharp
// Insira uma célula de tamanho relativo (porcentagem).
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

A largura desta célula será de 20% da largura total da tabela, tornando-a adaptável a diferentes tamanhos de tela ou layouts de documentos.

### Etapa 4: inserir uma célula de tamanho automático

Por fim, insira uma célula que se dimensione automaticamente com base no espaço disponível restante na tabela.

```csharp
// Insira uma célula de tamanho automático.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

 O`PreferredWidth.Auto` A configuração permite que esta célula se expanda ou contraia com base no espaço deixado após as outras células serem contabilizadas. Isso garante que o layout da mesa pareça equilibrado e profissional.

## Etapa 5: finalizar e salvar o documento

Depois de inserir todas as células, preencha a tabela e salve o documento no caminho especificado.

```csharp
// Salve o documento.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Esta etapa finaliza a tabela e salva o documento com o nome de arquivo "WorkingWithTables.PreferredWidthSettings.docx" no diretório designado.

## Conclusão

Criar tabelas com configurações de largura preferidas no Aspose.Words for .NET é simples quando você entende as diferentes opções de dimensionamento disponíveis. Se você precisa de larguras de células fixas, relativas ou automáticas, Aspose.Words oferece flexibilidade para lidar com vários cenários de layout de tabela com eficiência. Seguindo as etapas descritas neste guia, você pode garantir que suas tabelas estejam bem estruturadas e visualmente atraentes em seus documentos do Word.

## Perguntas frequentes

### Qual é a diferença entre larguras de células absolutas e relativas?
As larguras absolutas das células são fixas e não mudam, enquanto as larguras relativas são ajustadas com base na largura total da tabela.

### Posso usar porcentagens negativas para larguras relativas?
Não, porcentagens negativas não são válidas para larguras de células. Somente percentagens positivas são permitidas.

### Como funciona o recurso de dimensionamento automático?
O dimensionamento automático ajusta a largura da célula para preencher qualquer espaço restante na tabela após o dimensionamento de outras células.

### Posso aplicar estilos diferentes a células com configurações de largura diferentes?
Sim, você pode aplicar vários estilos e formatação às células, independentemente de suas configurações de largura.

### O que acontece se a largura total da tabela for menor que a soma de todas as larguras das células?
A tabela ajustará automaticamente a largura das células para caber no espaço disponível, o que pode fazer com que algumas células diminuam.