---
title: Unidade de medida
linktitle: Unidade de medida
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como configurar o recurso de unidade de medida no Aspose.Words for .NET para preservar a formatação do documento durante a conversão ODT.
type: docs
weight: 10
url: /pt/net/programming-with-odtsaveoptions/measure-unit/
---
## Introdução

Você já teve que converter seus documentos do Word para formatos diferentes, mas precisava de uma unidade de medida específica para o seu layout? Esteja você lidando com polegadas, centímetros ou pontos, é crucial garantir que seu documento mantenha sua integridade durante o processo de conversão. Neste tutorial, veremos como configurar o recurso de unidade de medida no Aspose.Words for .NET. Este poderoso recurso garante que a formatação do seu documento seja preservada exatamente como você precisa ao converter para o formato ODT (Open Document Text).

## Pré-requisitos

Antes de mergulhar no código, há algumas coisas que você precisa para começar:

1. Aspose.Words for .NET: Certifique-se de ter a versão mais recente do Aspose.Words for .NET instalada. Se você ainda não o possui, pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: um IDE como o Visual Studio para escrever e executar seu código C#.
3. Conhecimento básico de C#: Compreender os conceitos básicos de C# o ajudará a acompanhar o tutorial.
4. Um documento do Word: tenha um documento do Word de amostra pronto para ser usado na conversão.

## Importar namespaces

Antes de começarmos a codificar, vamos nos certificar de que importamos os namespaces necessários. Adicione-os usando diretivas no topo do seu arquivo de código:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa definir o caminho para o diretório do seu documento. É aqui que o seu documento Word está localizado e onde o arquivo convertido será salvo.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real para o seu diretório. Isso garante que seu código saiba onde encontrar seu documento do Word.

## Etapa 2: carregue o documento do Word

 Em seguida, você precisa carregar o documento do Word que deseja converter. Isto é feito usando o`Document` classe de Aspose.Words.

```csharp
// Carregue o documento do Word
Document doc = new Document(dataDir + "Document.docx");
```

Certifique-se de que seu documento do Word, denominado "Document.docx", esteja presente no diretório especificado.

## Passo 3: Configurar a Unidade de Medida

 Agora vamos configurar a unidade de medida para a conversão ODT. É aqui que a mágica acontece. Vamos configurar o`OdtSaveOptions` usar polegadas como unidade de medida.

```csharp
// Configuração de opções de backup com recurso “Unidade de medida”
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 Neste exemplo, estamos definindo a unidade de medida para polegadas. Você também pode escolher outras unidades, como`OdtSaveMeasureUnit.Centimeters` ou`OdtSaveMeasureUnit.Points` dependendo de suas necessidades.

## Etapa 4: converter o documento em ODT

 Finalmente, converteremos o documento Word para o formato ODT usando o configurado`OdtSaveOptions`.

```csharp
// Converta o documento para ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Esta linha de código salva o documento convertido no diretório especificado com a nova unidade de medida aplicada.

## Conclusão

aí está! Seguindo essas etapas, você pode configurar facilmente o recurso de unidade de medida no Aspose.Words for .NET para garantir que o layout do seu documento seja preservado durante a conversão. Esteja você trabalhando com polegadas, centímetros ou pontos, este tutorial mostrou como controlar a formatação do seu documento com facilidade.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para trabalhar programaticamente com documentos do Word. Ele permite que os desenvolvedores criem, modifiquem, convertam e processem documentos do Word sem a necessidade do Microsoft Word.

### Posso usar outras unidades de medida além de polegadas?
 Sim, Aspose.Words for .NET suporta outras unidades de medida, como centímetros e pontos. Você pode especificar a unidade desejada usando o`OdtSaveMeasureUnit` enumeração.

### Existe um teste gratuito disponível para Aspose.Words for .NET?
 Sim, você pode baixar uma avaliação gratuita do Aspose.Words for .NET em[aqui](https://releases.aspose.com/).

### Onde posso encontrar documentação para Aspose.Words for .NET?
 Você pode acessar a documentação abrangente do Aspose.Words for .NET em[este link](https://reference.aspose.com/words/net/).

### Como posso obter suporte para Aspose.Words for .NET?
 Para suporte, você pode visitar o fórum Aspose.Words em[este link](https://forum.aspose.com/c/words/8).
