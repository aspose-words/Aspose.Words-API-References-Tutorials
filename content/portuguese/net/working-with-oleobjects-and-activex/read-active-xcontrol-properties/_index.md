---
title: Leia as propriedades ativas do XControl no arquivo Word
linktitle: Leia as propriedades ativas do XControl no arquivo Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ler propriedades de controle ActiveX de arquivos do Word usando Aspose.Words for .NET em um guia passo a passo. Aprimore suas habilidades de automação de documentos.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## Introdução

Na era digital de hoje, a automação é fundamental para aumentar a produtividade. Se você estiver trabalhando com documentos do Word que contêm controles ActiveX, talvez seja necessário ler suas propriedades para diversos fins. Os controles ActiveX, como caixas de seleção e botões, podem conter dados importantes. Usando Aspose.Words for .NET, você pode extrair e manipular esses dados de maneira eficiente e programática.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Biblioteca Aspose.Words for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
2. Visual Studio ou qualquer IDE C#: para escrever e executar seu código.
3. Um documento do Word com controles ActiveX: por exemplo, "Controles ActiveX.docx".
4. Conhecimento básico de C#: É necessário ter familiaridade com programação C# para acompanhar.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários para trabalhar com Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Etapa 1: carregue o documento do Word

Para começar, você precisará carregar o documento do Word que contém os controles ActiveX.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Etapa 2: inicializar uma string para manter propriedades

A seguir, inicialize uma string vazia para armazenar as propriedades dos controles ActiveX.

```csharp
string properties = "";
```

## Etapa 3: iterar pelas formas do documento

Precisamos percorrer todas as formas do documento para encontrar os controles ActiveX.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // Processar o controle ActiveX
    }
}
```

## Etapa 4: extrair propriedades dos controles ActiveX

Dentro do loop, verifique se o controle é um Forms2OleControl. Se for, lance-o e extraia as propriedades.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Etapa 5: contar o total de controles ActiveX

Após iterar todas as formas, conte o número total de controles ActiveX encontrados.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Etapa 6: exibir as propriedades

Por fim, imprima as propriedades extraídas no console.

```csharp
Console.WriteLine("\n" + properties);
```

## Conclusão

aí está! Você aprendeu com sucesso como ler propriedades de controle ActiveX de um documento do Word usando Aspose.Words for .NET. Este tutorial abordou o carregamento de um documento, a iteração por formas e a extração de propriedades de controles ActiveX. Seguindo essas etapas, você pode automatizar a extração de dados importantes de seus documentos do Word, aumentando a eficiência do seu fluxo de trabalho.

## Perguntas frequentes

### O que são controles ActiveX em documentos do Word?
Os controles ActiveX são objetos interativos incorporados em documentos do Word, como caixas de seleção, botões e campos de texto, usados para criar formulários e automatizar tarefas.

### Posso modificar as propriedades dos controles ActiveX usando Aspose.Words for .NET?
Sim, Aspose.Words for .NET permite modificar as propriedades dos controles ActiveX programaticamente.

### O uso do Aspose.Words for .NET é gratuito?
 Aspose.Words for .NET oferece uma avaliação gratuita, mas você precisará adquirir uma licença para uso continuado. Você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Posso usar Aspose.Words for .NET com outras linguagens .NET além de C#?
Sim, Aspose.Words for .NET pode ser usado com qualquer linguagem .NET, incluindo VB.NET e F#.

### Onde posso encontrar mais documentação sobre Aspose.Words for .NET?
 Você pode encontrar documentação detalhada[aqui](https://reference.aspose.com/words/net/).