---
title: Limpar estilos e listas não utilizados
linktitle: Limpar estilos e listas não utilizados
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para limpar estilos e listas não utilizados em um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

Neste tutorial, orientaremos você no código-fonte C# para limpar estilos e listas não utilizados com Aspose.Words for .NET. Este recurso permite remover estilos e listas que não são usados em um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa, carregaremos o documento Word contendo os estilos e listas não utilizados que queremos limpar. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: conte estilos e listas antes de limpar

Antes da limpeza, contaremos a quantidade de estilos e listas presentes no documento. Use o seguinte código para exibir os contadores:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Estas instruções mostram a quantidade de estilos e listas presentes no documento antes da limpeza.

## Etapa 4: limpe estilos e listas não utilizados

Agora vamos limpar estilos e listas não utilizados do documento. Use o seguinte código para realizar a limpeza:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Este código limpa estilos e listas não utilizados do documento usando as opções especificadas. Neste exemplo, habilitamos o`UnusedStyles` opção para remover estilos não utilizados e desabilitou o`UnusedLists` opção de manter as listas mesmo que não sejam usadas.

## Etapa 5: contar estilos e listas após a limpeza

Após fazer a limpeza, contaremos novamente os estilos e listas para verificar se foram recolhidos. Use o código a seguir para exibir os novos contadores:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Estas instruções mostram os números de estilos e listas restantes após a limpeza.

### Exemplo de código-fonte para limpar estilos e listas não utilizados usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Combinado com os estilos integrados, o documento agora possui oito estilos.
	// Um estilo personalizado é marcado como "usado" enquanto houver texto no documento
	// formatado nesse estilo. Isso significa que os 4 estilos que adicionamos não estão em uso no momento.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	// Limpa estilos e listas não utilizados do documento dependendo de CleanupOptions fornecidas.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como limpar estilos e listas não utilizados de um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode aplicar facilmente esse recurso aos seus próprios documentos.

