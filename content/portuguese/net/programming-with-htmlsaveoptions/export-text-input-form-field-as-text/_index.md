---
title: Exportar campo de formulário de entrada de texto como texto
linktitle: Exportar campo de formulário de entrada de texto como texto
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para exportar campos de formulário de entrada de texto como texto simples com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

Neste tutorial, orientaremos você através do código-fonte C# para exportar campos de formulário de entrada de texto como texto simples com Aspose.Words for .NET. Este recurso permite exportar campos de formulário de entrada de texto como texto legível, em vez de exportá-los como elementos de entrada HTML.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento para exportar. Use o código a seguir para carregar o documento de um diretório especificado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Este código cria uma instância de`Document` carregando o documento do diretório especificado.

## Etapa 3: configurar opções de backup HTML

Agora configuraremos as opções de salvamento de HTML para exportar campos de formulário de entrada de texto como texto simples. Use o seguinte código:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// A pasta especificada deve existir e estar vazia.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Este código cria uma instância de`HtmlSaveOptions` e define o`ExportTextInputFormFieldAsText` opção para`true` para exportar campos de formulário de entrada de texto como texto simples. Além disso, especifica a pasta onde as imagens extraídas serão salvas.

## Passo 4: Convertendo e salvando o documento em HTML

Por fim, converteremos o documento em HTML usando as opções de salvamento de HTML configuradas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Este código converte o documento em HTML exportando campos de formulário de entrada de texto como texto simples e salva o arquivo HTML exportado no diretório especificado.

### Exemplo de código-fonte para exportar campo de formulário de entrada de texto como texto usando Aspose.Words for .NET


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// A pasta especificada precisa existir e deve estar vazia.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Defina uma opção para exportar campos de formulário como texto simples, não como elementos de entrada HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Certifique-se de especificar o caminho correto para o diretório de documentos no arquivo`dataDir` variável.