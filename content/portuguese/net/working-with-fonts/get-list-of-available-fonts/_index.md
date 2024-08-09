---
title: Obtenha uma lista de fontes disponíveis
linktitle: Obtenha uma lista de fontes disponíveis
second_title: API de processamento de documentos Aspose.Words
description: Descubra como obter uma lista de fontes disponíveis usando Aspose.Words for .NET neste tutorial passo a passo detalhado. Aumente suas habilidades de gerenciamento de fontes.
type: docs
weight: 10
url: /pt/net/working-with-fonts/get-list-of-available-fonts/
---
## Introdução

Você já teve dificuldades para gerenciar fontes em seus documentos do Word? Se você é um desenvolvedor .NET, Aspose.Words for .NET está aqui para resgatá-lo! Esta poderosa biblioteca não apenas ajuda a criar e manipular documentos do Word de forma programática, mas também oferece amplos recursos de gerenciamento de fontes. Neste guia, orientaremos você em um tutorial passo a passo sobre como obter uma lista de fontes disponíveis usando Aspose.Words for .NET. Vamos dividi-lo em etapas fáceis de entender para garantir que você possa acompanhar com facilidade. Então, vamos mergulhar e tornar o gerenciamento de fontes muito fácil!

## Pré-requisitos

Antes de começarmos, existem algumas coisas que você precisará:

-  Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words for .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
- Visual Studio: este exemplo usa o Visual Studio como ambiente de desenvolvimento.
- .NET Framework: certifique-se de ter o .NET Framework instalado em sua máquina.
- Diretório de documentos: um caminho de diretório onde seus documentos são armazenados.

## Importar namespaces

Primeiro, importe os namespaces necessários para o seu projeto:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Etapa 1: inicializar as configurações de fonte

primeira etapa é inicializar as configurações de fonte. Isso permitirá que você gerencie as fontes de fontes de seus documentos.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: esta classe é usada para especificar as configurações para substituição de fontes e fontes de fontes.
- fontSources: criamos uma lista de fontes de fontes existentes a partir das configurações de fonte atuais.

## Etapa 2: definir o diretório de documentos

Em seguida, especifique o caminho para o diretório do seu documento. É aqui que o Aspose.Words pesquisará as fontes.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: esta variável de string contém o caminho para o diretório onde suas fontes estão localizadas. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real.

## Etapa 3: adicionar pasta de fontes personalizadas

Agora, adicione uma nova fonte de pasta para instruir Aspose.Words a pesquisar fontes nesta pasta.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: esta classe representa uma fonte de fonte de pasta. O segundo parâmetro (`true`) indica se as fontes devem ser pesquisadas recursivamente em subpastas.

## Etapa 4: atualizar as fontes das fontes

Adicione a pasta de fontes personalizadas à lista de fontes de fontes existentes e atualize as configurações de fonte.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource): Adiciona a pasta de fontes personalizadas às fontes de fontes existentes.
- atualizadoFontSources: converte a lista de fontes de fontes em um array.

## Etapa 5: recuperar e exibir fontes

Por fim, recupere as fontes disponíveis e exiba seus detalhes.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): recupera a lista de fontes disponíveis da primeira fonte de fonte na lista atualizada.
-  fontInfo: uma instância de`PhysicalFontInfo` contendo detalhes sobre cada fonte.

## Conclusão

Parabéns! Você recuperou com sucesso uma lista de fontes disponíveis usando Aspose.Words for .NET. Este tutorial orientou você em cada etapa, desde a inicialização das configurações de fonte até a exibição dos detalhes da fonte. Com esse conhecimento, agora você pode gerenciar fontes em seus documentos do Word com facilidade. Lembre-se de que Aspose.Words for .NET é uma ferramenta poderosa que pode aprimorar significativamente suas capacidades de processamento de documentos. Então vá em frente e explore mais recursos para tornar seu processo de desenvolvimento ainda mais eficiente.

## Perguntas frequentes

### Posso usar o Aspose.Words for .NET com outras estruturas .NET?
Sim, Aspose.Words for .NET é compatível com vários frameworks .NET, incluindo .NET Core e .NET 5+.

### Como instalo o Aspose.Words para .NET?
Você pode instalá-lo por meio do NuGet Package Manager no Visual Studio procurando por "Aspose.Words".

### É possível adicionar várias pastas de fontes personalizadas?
 Sim, você pode adicionar várias pastas de fontes personalizadas criando vários`FolderFontSource` instâncias e adicioná-las à lista de fontes de fontes.

### Posso recuperar detalhes de fontes de uma fonte específica?
 Sim, você pode recuperar detalhes da fonte de qualquer fonte especificando o índice da fonte no campo`updatedFontSources` variedade.

### O Aspose.Words for .NET suporta substituição de fontes?
Sim, ele oferece suporte à substituição de fontes para garantir que o texto seja renderizado corretamente, mesmo que a fonte original não esteja disponível.