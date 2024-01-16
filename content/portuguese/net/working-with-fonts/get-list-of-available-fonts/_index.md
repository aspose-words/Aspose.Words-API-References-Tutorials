---
title: Obtenha uma lista de fontes disponíveis
linktitle: Obtenha uma lista de fontes disponíveis
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como obter a lista de fontes disponíveis no Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/get-list-of-available-fonts/
---
Neste tutorial, explicaremos como obter a lista de fontes disponíveis no Aspose.Words for .NET. A lista de fontes disponíveis permite saber quais fontes você pode usar em seus documentos. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto

## Passo 1: Defina o diretório do documento
 Primeiro, você precisa definir o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: configurar fontes de fontes
 A seguir, criaremos uma instância de`FontSettings` e obtenha as fontes de fontes existentes usando o`GetFontsSources()` método. Também adicionaremos uma nova fonte de fonte especificando uma pasta que contém as fontes.

```csharp
// Configurar fontes de fontes
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Adicione uma nova fonte de fonte
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Etapa 3: obtenha a lista de fontes disponíveis
 Agora vamos navegar pelas fontes disponíveis usando o`GetAvailableFonts()` método na primeira fonte de fonte atualizada.

```csharp
// Obtenha a lista de fontes disponíveis
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Exemplo de código-fonte para obter lista de fontes disponíveis usando Aspose.Words for .NET 

```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Adicione uma nova fonte de pasta que instruirá Aspose.Words a pesquisar fontes na seguinte pasta.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Adicione a pasta personalizada que contém nossas fontes à lista de fontes de fontes existentes.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Conclusão
Neste tutorial, vimos como obter a lista de fontes disponíveis no Aspose.Words for .NET. Isso permite que você saiba quais fontes você pode usar em seus documentos. Sinta-se à vontade para usar este recurso para escolher fontes apropriadas para suas necessidades.

### Perguntas frequentes

#### P: Como posso recuperar a lista de fontes disponíveis no Aspose.Words?

 R: Para recuperar a lista de fontes disponíveis no Aspose.Words, você pode usar o`FontsProvider` classe e o`GetAvailableFonts` método. Este método retornará uma lista de todas as fontes instaladas em seu sistema.

#### P: Posso filtrar a lista de fontes disponíveis por determinados critérios no Aspose.Words?

R: Sim, você pode filtrar a lista de fontes disponíveis no Aspose.Words usando critérios específicos. Por exemplo, você pode filtrar fontes por família, estilo ou idioma.

#### P: Como posso usar a lista de fontes disponíveis em meus documentos do Word?

 R: Para usar a lista de fontes disponíveis em seus documentos do Word, você pode navegar na lista e selecionar as fontes apropriadas usando os métodos e propriedades do arquivo Word.`FontSettings` classe em Aspose.Words.