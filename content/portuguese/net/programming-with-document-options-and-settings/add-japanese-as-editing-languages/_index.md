---
title: Adicionar japonês como idioma de edição
linktitle: Adicionar japonês como idioma de edição
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para adicionar japonês como idioma de edição com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Neste tutorial, iremos guiá-lo passo a passo para entender e implementar a funcionalidade de adicionar japonês como linguagem de edição com Aspose.Words for .NET. Este recurso permite definir preferências de idioma ao carregar um documento e adicionar japonês como idioma de edição.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word que não contém um idioma de edição padrão e ao qual queremos adicionar o japonês. Use o seguinte código para carregar o documento:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Defina as preferências de idioma que serão usadas ao carregar o documento.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Etapa 3: verificar o idioma padrão

Após carregar o documento, verificaremos se o idioma de edição padrão foi configurado corretamente para japonês. Use o código a seguir para obter o ID do idioma do Extremo Oriente:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

O código verifica se o ID do idioma do Extremo Oriente corresponde ao japonês. De acordo com o resultado, exibe uma mensagem correspondente.

### Exemplo de código-fonte para adicionar japonês como idiomas de edição usando Aspose.Words for .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Defina as preferências de idioma que serão usadas quando o documento for carregado.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

