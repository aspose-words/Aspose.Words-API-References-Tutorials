---
title: Definir pasta de fontes True Type
linktitle: Definir pasta de fontes True Type
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir a pasta de fontes True Type ao renderizar um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-true-type-fonts-folder/
---

Neste tutorial, orientaremos você no processo passo a passo para definir a pasta de fontes true type ao renderizar um documento usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como especificar uma pasta personalizada contendo fontes True Type para usar ao renderizar seus documentos usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento renderizado editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento para renderizar
 Em seguida, você precisa carregar o documento para renderizar usando o`Document` aula. Certifique-se de especificar o caminho correto do documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: definir a pasta de fontes True Type
Agora você pode especificar a pasta de fontes True Type a serem usadas durante a renderização, criando uma instância do`FontSettings` classe e usando o`SetFontsFolder()` método para definir a pasta de fontes. Você pode especificar uma pasta personalizada contendo suas fontes True Type. O segundo parâmetro a`SetFontsFolder()` indica se você também deseja pesquisar subpastas da pasta especificada.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Etapa 4: salve o documento renderizado
 Finalmente, você pode salvar o documento renderizado em um arquivo usando o`Save()` método do`Document` aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Exemplo de código-fonte para definir pasta de fontes True Type usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Observe que esta configuração substituirá qualquer fonte de fonte padrão que esteja sendo pesquisada por padrão. Agora apenas essas pastas serão pesquisadas
// Fontes ao renderizar ou incorporar fontes. Para adicionar uma fonte de fonte extra enquanto mantém as fontes de fonte do sistema, use FontSettings.GetFontSources e
// FontSettings.SetFontSources em vez disso
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Definir configurações de fonte
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusão
Neste tutorial, aprendemos como definir a pasta de fontes true type ao renderizar um documento usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode especificar facilmente uma pasta personalizada contendo fontes True Type para usar ao renderizar seus documentos. Aspose.Words oferece uma API poderosa e flexível para processamento de palavras com fontes em seus documentos. Com esse conhecimento, você pode controlar e personalizar as fontes usadas ao renderizar seus documentos de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso configurar a pasta de fontes TrueType em Aspose.Words?

 R: Para configurar a pasta de fontes TrueType no Aspose.Words, você pode usar o`SetTrueTypeFontsFolder` método do`Fonts` classe especificando o local da pasta que contém as fontes TrueType.

#### P: Que tipos de fontes são consideradas fontes TrueType?

R: As fontes TrueType são um formato de fonte popular. Eles são frequentemente usados em documentos do Word e possuem uma extensão de arquivo .ttf ou .ttc.

#### P: Posso especificar várias pastas de fontes TrueType em Aspose.Words?

R: Sim, você pode especificar várias pastas de fontes TrueType em Aspose.Words usando o`SetTrueTypeFontsFolder` método do`Fonts` class com uma lista de locais de pastas.

#### P: Como posso verificar a pasta de fontes TrueType configurada em Aspose.Words?

 R: Para verificar a pasta TrueType Fonts configurada em Aspose.Words, você pode usar o`GetTrueTypeFontsFolder` método do`Fonts` class para obter a localização da pasta TrueType Fonts configurada.

#### P: Por que é importante configurar a pasta de fontes TrueType no Aspose.Words?

R: Configurar a pasta de fontes TrueType no Aspose.Words é importante porque ajuda o Aspose.Words a localizar as fontes necessárias ao processar documentos do Word. Isso garante consistência na formatação e aparência dos documentos, mesmo em sistemas diferentes.