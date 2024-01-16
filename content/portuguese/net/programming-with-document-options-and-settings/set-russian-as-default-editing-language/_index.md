---
title: Definir russo como idioma de edição padrão
linktitle: Definir russo como idioma de edição padrão
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir o russo como idioma de edição padrão de um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

Neste tutorial, orientaremos você através do código-fonte C# para definir o russo como o idioma de edição padrão com Aspose.Words for .NET. Este recurso permite definir o idioma padrão ao carregar um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa, carregaremos o documento Word para o qual queremos definir o russo como idioma de edição padrão. Use o seguinte código para carregar o documento:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: verificar o idioma padrão

Após o upload do documento, verificaremos se o idioma padrão foi definido corretamente para russo. Use o código a seguir para obter o ID do idioma padrão:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

O código verifica se o ID do idioma corresponde ao russo. De acordo com o resultado, exibe uma mensagem correspondente.

### Exemplo de código-fonte para definir russo como idioma de edição padrão usando Aspose.Words for .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como definir o russo como idioma de edição padrão para um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo