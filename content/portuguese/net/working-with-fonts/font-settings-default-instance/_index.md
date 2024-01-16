---
title: Instância padrão de configurações de fonte
linktitle: Instância padrão de configurações de fonte
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como definir as configurações de fonte padrão em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/font-settings-default-instance/
---

Neste tutorial, orientaremos você sobre como definir as configurações de fonte padrão em um documento do Word usando a biblioteca Aspose.Words para .NET. As configurações de fonte padrão permitem especificar as fontes de fonte usadas ao carregar e renderizar documentos. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

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

## Etapa 2: definir configurações de fonte padrão
 A seguir, criaremos uma instância de`FontSettings` usando`FontSettings.DefaultInstance`e então especificaremos as fontes de fontes usadas ao carregar e renderizar documentos. Neste exemplo, estamos usando uma fonte de fonte do sistema e uma fonte de fonte de pasta.

```csharp
// Definir configurações de fonte padrão
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Etapa 3: fazer upload do documento com configurações de fonte
 Agora vamos carregar o documento usando`LoadOptions` e especificando as configurações de fonte a serem usadas.

```csharp
// Carregue o documento com as configurações de fonte
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Exemplo de código-fonte para instância padrão de configurações de fonte usando Aspose.Words for .NET 
```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusão
Neste tutorial, vimos como definir as configurações de fonte padrão em um documento do Word com Aspose.Words for .NET. Ao especificar as fontes de fontes usadas ao carregar e renderizar documentos, você pode controlar a aparência das fontes em seus documentos. Sinta-se à vontade para usar este recurso para personalizar as configurações de fonte em seus projetos.

### Perguntas frequentes

#### P: Como posso definir a fonte padrão no Aspose.Words?

 R: Para definir a fonte padrão no Aspose.Words, você pode usar o`FontSettings` classe e o`DefaultFontName` propriedade especificando o nome da fonte desejada.

#### P: Posso especificar o tamanho da fonte padrão em Aspose.Words?

 R: Sim, você pode especificar o tamanho da fonte padrão no Aspose.Words usando o`DefaultFontSize` propriedade do`FontSettings` aula. Você pode definir o tamanho de ponto desejado.

#### P: É possível definir a cor da fonte padrão no Aspose.Words?

 R: Sim, você pode definir a cor da fonte padrão no Aspose.Words usando o`DefaultColor` propriedade do`FontSettings` aula. Você pode especificar a cor usando valores RGB ou nomes predefinidos.

#### P: As configurações de fonte padrão se aplicam a todos os documentos?

R: Sim, as configurações de fonte padrão se aplicam a todos os documentos criados ou editados no Aspose.Words, a menos que configurações específicas sejam definidas para um documento individual.