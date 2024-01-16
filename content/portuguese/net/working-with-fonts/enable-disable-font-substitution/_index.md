---
title: Habilitar Desabilitar Substituição de Fonte
linktitle: Habilitar Desabilitar Substituição de Fonte
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como ativar ou desativar a substituição de fonte em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/enable-disable-font-substitution/
---
Neste tutorial, orientaremos você sobre como ativar ou desativar a substituição de fonte em um documento do Word ao renderizá-lo usando a biblioteca Aspose.Words para .NET. Ativar ou desativar a substituição de fontes permite controlar se as fontes ausentes serão substituídas automaticamente por uma fonte padrão. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto
- Um documento do Word que você deseja renderizar com ou sem substituição de fonte

## Passo 1: Defina o diretório do documento
 Primeiro, você precisa definir o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: carregue o documento e defina as configurações de fonte
 A seguir, carregaremos o documento Word que você deseja renderizar e criaremos uma instância do`FontSettings` class para lidar com as configurações de fonte. Definiremos a substituição da fonte padrão especificando o nome da fonte em`DefaultFontName` e desative a substituição de informações de fonte com`Enabled` definido como`false`.

```csharp
// Carregue o documento
Document doc = new Document(dataDir + "Rendering.docx");

// Definir configurações de fonte
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Aplicar as configurações de fonte ao documento
doc.FontSettings = fontSettings;
```

## Etapa 3: salve o documento renderizado
Por fim, salvaremos o documento renderizado, que respeitará as configurações de substituição de fonte definidas.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Exemplo de código-fonte para ativar e desativar substituição de fonte usando Aspose.Words for .NET 

```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Conclusão
Neste tutorial, vimos como ativar ou desativar a substituição de fonte em um documento do Word ao renderizá-lo com Aspose.Words for .NET. Ao controlar a substituição de fontes, você pode influenciar como as fontes ausentes são tratadas nos documentos renderizados. Não hesite em usar este recurso para personalizar o gerenciamento de fontes em seus documentos Word.

### Perguntas frequentes

#### P: Como posso ativar a substituição de fonte em um documento do Word com Aspose.Words?

R: Para habilitar a substituição de fontes em um documento do Word com Aspose.Words, você pode usar a API para especificar fontes de substituição a serem usadas quando as fontes necessárias não estiverem disponíveis. Isso garantirá uma visualização consistente do texto, mesmo sem as fontes originais.

#### P: É possível desabilitar a substituição de fonte em um documento do Word com Aspose.Words?

R: Sim, com Aspose.Words você pode desabilitar a substituição de fonte em um documento do Word. Ao usar a API, você pode evitar que o Word substitua as fontes necessárias por outras fontes, o que mantém a aparência original do texto.

#### P: O que acontece quando faltam as fontes necessárias durante a substituição em um documento do Word?

R: Quando as fontes necessárias estão faltando durante a substituição em um documento do Word, o Aspose.Words pode detectar esse problema e fornecer opções para corrigi-lo. Você pode optar por substituir as fontes ausentes por fontes alternativas ou incluir as fontes ausentes no documento, garantindo a visualização correta.

#### P: Como posso lidar com fontes ausentes ao substituí-las em um documento do Word por Aspose.Words?

R: Para lidar com fontes ausentes ao substituir um documento do Word por Aspose.Words, você pode usar a API para detectar fontes ausentes e fornecer opções de resolução. Você pode optar por substituir as fontes ausentes por fontes alternativas ou incluir fontes ausentes no documento, dependendo de suas necessidades.

#### P: É importante controlar a substituição de fontes em um documento do Word?

R: Sim, é importante controlar a substituição de fontes em um documento Word para manter a integridade visual do texto. Ao usar Aspose.Words para ativar ou desativar a substituição de fontes, você pode garantir que as fontes necessárias sejam usadas e evitar problemas com fontes ausentes ou substituídas.