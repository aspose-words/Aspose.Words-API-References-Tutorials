---
title: Definir sistema de pastas de fontes e pasta personalizada
linktitle: Definir sistema de pastas de fontes e pasta personalizada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir pastas de sistema e de fontes personalizadas em documentos do Word usando Aspose.Words for .NET, garantindo que seus documentos sejam exibidos corretamente em diferentes ambientes.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Introdução

Imagine que você está criando um documento com um estilo de fonte exclusivo, apenas para descobrir que as fontes não são exibidas corretamente em outra máquina. Frustrante, certo? É aqui que entra em jogo a configuração das pastas de fontes. Com Aspose.Words for .NET, você pode definir pastas de sistema e de fontes personalizadas para garantir que seus documentos sempre tenham a aparência desejada. Vamos ver como você pode conseguir isso.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Biblioteca Aspose.Words for .NET: se ainda não o fez, faça o download[aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: um IDE como o Visual Studio.
- Conhecimento básico de C#: A familiaridade com C# o ajudará a acompanhar os exemplos de código.

## Importar namespaces

Primeiro, importe os namespaces necessários para o seu projeto:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Agora, vamos dividir o processo em etapas simples.

## Etapa 1: carregue o documento

 Para começar, carregue seu documento do Word em um Aspose.Words`Document` objeto. Este documento será aquele onde você deseja definir as pastas de fontes.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 2: inicializar as configurações de fonte

 Crie uma nova instância de`FontSettings`. Este objeto permitirá que você gerencie fontes de fontes.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Etapa 3: recuperar fontes de fontes do sistema

Recuperar as fontes de fonte padrão do sistema. Em uma máquina Windows, isso normalmente inclui o "Windows\Fonts\"diretório.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Etapa 4: adicionar uma pasta de fontes personalizadas

Adicione uma pasta personalizada que contenha suas fontes adicionais. Isso é útil se você tiver fontes específicas não instaladas no diretório de fontes do sistema.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Etapa 5: atualizar as fontes das fontes

 Converta a lista de fontes de fontes de volta em um array e defina-a como`FontSettings` objeto.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Etapa 6: aplicar configurações de fonte ao documento

 Por fim, aplique o configurado`FontSettings` ao seu documento e salve-o no formato desejado, como PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusão

aí está! Seguindo essas etapas, você pode garantir que seus documentos do Word usem as fontes corretas, sejam elas do sistema ou personalizadas armazenadas em um diretório específico. Esta configuração ajuda a manter a integridade da aparência do seu documento em diferentes ambientes.

## Perguntas frequentes

### O que acontece se uma fonte estiver faltando nas pastas do sistema e nas pastas personalizadas?

Aspose.Words usará uma fonte padrão para substituir a fonte ausente, garantindo que o documento permaneça legível.

### Posso adicionar várias pastas de fontes personalizadas?

 Sim, você pode adicionar várias pastas de fontes personalizadas repetindo o processo de criação`FolderFontSource` objetos e adicioná-los à lista de fontes de fontes.

### É possível usar caminhos de rede para pastas de fontes personalizadas?

 Sim, você pode especificar um caminho de rede no`FolderFontSource` construtor.

### Quais formatos de arquivo o Aspose.Words suporta para salvar documentos?

Aspose.Words suporta vários formatos, incluindo DOCX, PDF, HTML e muito mais.

### Como lidar com notificações de substituição de fontes?

 Você pode lidar com notificações de substituição de fonte usando o`FontSettings` aula`FontSubstitutionWarning`evento.