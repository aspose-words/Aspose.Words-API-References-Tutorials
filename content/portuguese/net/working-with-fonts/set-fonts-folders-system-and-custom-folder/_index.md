---
title: Definir sistema de pastas de fontes e pasta personalizada
linktitle: Definir sistema de pastas de fontes e pasta personalizada
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para configurar pastas de sistema e de fontes personalizadas ao renderizar um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

Neste tutorial, orientaremos você no processo passo a passo para definir pastas de fontes do sistema e uma pasta personalizada ao renderizar um documento usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como especificar várias pastas de fontes, incluindo a pasta do sistema e uma pasta personalizada, para usar ao renderizar seus documentos usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento renderizado editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento para renderizar
 Então você pode carregar o documento para renderizar usando o`Document` aula. Certifique-se de especificar o caminho correto do documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: definir pastas de sistema e de fontes personalizadas
 Agora você pode definir pastas de fontes do sistema e uma pasta personalizada usando o`FontSettings` classe e o`SetFontsSources()` método. Primeiro, você precisa recuperar a lista de fontes de fontes dependentes do ambiente usando`GetFontsSources()` e armazene-o em uma lista. Então você pode criar uma nova instância de`FolderFontSource` especificando o caminho para a pasta personalizada que contém suas fontes. Adicione esta instância à lista de fontes de fontes existentes. Finalmente, use`SetFontsSources()` para atualizar as fontes de fontes com a nova lista.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Etapa 4: aplicar configurações de fonte
 Em seguida, você precisa aplicar as configurações de fonte ao seu documento usando o`FontSettings` propriedade do`Document` aula.

```csharp
doc.FontSettings = fontSettings;
```

## Etapa 5: salve o documento renderizado
Finalmente, você pode salvar o documento renderizado em um arquivo clicando

   usando o`Save()` método do`Document` aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Exemplo de código-fonte para definir sistema de pastas de fontes e pasta personalizada usando Aspose.Words para .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Recuperar a matriz de fontes de fontes dependentes do ambiente que são pesquisadas por padrão.
// Por exemplo, isso conterá uma fonte "Windows\Fonts\" em máquinas Windows.
// Adicionamos esse array a uma nova Lista para tornar muito mais fácil adicionar ou remover entradas de fonte.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Adicione uma nova fonte de pasta que instruirá Aspose.Words a pesquisar fontes na seguinte pasta.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Adicione a pasta personalizada que contém nossas fontes à lista de fontes de fontes existentes.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusão
Neste tutorial, aprendemos como definir pastas de fontes do sistema e uma pasta personalizada ao renderizar um documento usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode especificar facilmente várias pastas de fontes, incluindo a pasta do sistema e uma pasta personalizada, para usar ao renderizar seus documentos. Aspose.Words oferece uma API poderosa e flexível para processamento de palavras com fontes em seus documentos. Com esse conhecimento, você pode controlar e personalizar as fontes de fontes usadas ao renderizar seus documentos de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso definir pastas de fontes do sistema em Aspose.Words?

R: Para definir pastas de fontes do sistema no Aspose.Words, você não precisa fazer nada. Aspose.Words usa automaticamente fontes do sistema instaladas em seu sistema operacional.

#### P: Como posso definir pastas de fontes personalizadas no Aspose.Words?

 R: Para definir as pastas de fontes personalizadas no Aspose.Words, você pode usar o`SetFontsFolders` método do`Fonts` classe especificando os locais das pastas de fontes personalizadas.

#### P: Posso especificar várias pastas de fontes personalizadas em Aspose.Words?

 R: Sim, você pode especificar várias pastas de fontes personalizadas em Aspose.Words usando o`SetFontsFolders` método do`Fonts` class com uma lista de locais de pastas.

#### P: Como posso verificar as pastas de fontes definidas em Aspose.Words?

 Para verificar as pastas de fontes definidas em Aspose.Words, você pode usar o`GetFolders` método do`Fonts` class para obter a lista de pastas de fontes configuradas.

#### P: As fontes de pastas personalizadas têm prioridade sobre as fontes do sistema no Aspose.Words?

R: Sim, as fontes de pastas personalizadas têm prioridade sobre as fontes do sistema no Aspose.Words. Se uma fonte estiver presente nas pastas personalizadas e nas fontes do sistema, o Aspose.Words usará a versão da pasta personalizada.