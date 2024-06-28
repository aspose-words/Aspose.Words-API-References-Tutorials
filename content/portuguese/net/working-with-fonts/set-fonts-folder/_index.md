---
title: Definir pasta de fontes
linktitle: Definir pasta de fontes
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir o diretório de fontes no Aspose.Words for .NET e garantir a disponibilidade das fontes usadas em seus documentos.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-fonts-folder/
---
Neste tutorial, mostraremos como definir o diretório de fontes no Aspose.Words for .NET. Você aprenderá como especificar o diretório que contém as fontes usadas em seu documento do Word.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto

## Passo 1: Defina o diretório do documento
Comece definindo o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: definir o diretório de fontes
 Crie uma instância do`FontSettings` classe e use o`SetFontsFolder` método para especificar o diretório que contém as fontes. Substituir`"Fonts"` com o nome do diretório de fontes real.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Etapa 3: carregue o documento com configurações de fonte
 Use o`LoadOptions` classe para especificar configurações de fonte no`FontSettings` opção. Então use o`Document` class para carregar o documento usando essas opções.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Exemplo de código-fonte para definir pasta de fontes usando Aspose.Words for .NET 

```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusão
Parabéns! Agora você sabe como definir o diretório de fontes no Aspose.Words for .NET. Você pode usar esse recurso para garantir a disponibilidade das fontes usadas em seu documento e garantir consistência na exibição das fontes.

### Perguntas frequentes

#### P: Como posso definir uma pasta de fontes personalizada no Aspose.Words?

 R: Para definir uma pasta de fontes personalizadas no Aspose.Words, você pode usar o`FontsFolder` classe e o`SetFontsFolders` método especificando o caminho para a pasta que contém suas fontes.

#### P: Posso definir várias pastas de fontes no Aspose.Words?

 R: Sim, você pode definir várias pastas de fontes em Aspose.Words chamando o`SetFontsFolders` método várias vezes com os caminhos das diferentes pastas de fontes que você deseja usar.

#### P: O que acontece se uma fonte usada no documento não estiver presente nas pastas de fontes definidas?

R: Se uma fonte usada no documento não estiver presente nas pastas de fontes definidas em Aspose.Words, uma fonte substituta será usada. Isso garante que o texto do documento sempre será exibido corretamente, mesmo que a fonte original não esteja disponível.

#### P: As pastas de fontes definidas no Aspose.Words têm prioridade sobre as fontes instaladas no sistema?

R: Sim, as pastas de fontes definidas em Aspose.Words têm precedência sobre as fontes instaladas no sistema. Isso significa que se uma fonte com o mesmo nome estiver presente nas pastas de fontes definidas e nas fontes do sistema, a versão da pasta de fontes será usada no processamento de documentos do Word.