---
title: Limpar estilo duplicado
linktitle: Limpar estilo duplicado
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para limpar estilos duplicados em um documento usando Aspose.Words for .NET. Código fonte completo incluído.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

Neste tutorial, orientaremos você passo a passo no código-fonte C# para limpar estilos duplicados com Aspose.Words for .NET. Este recurso ajuda a remover estilos duplicados de um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word que queremos limpar. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: conte os estilos antes de limpar

Antes de prosseguir com a limpeza, contaremos a quantidade de estilos presentes no documento. Use o código a seguir para exibir a contagem de estilos:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Esta instrução exibe o número de estilos presentes no documento.

## Etapa 4: limpar estilos duplicados

Agora vamos limpar os estilos duplicados do documento. Use o seguinte código para realizar a limpeza:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Este código limpa estilos duplicados do documento usando as opções especificadas. Neste exemplo, habilitamos o`DuplicateStyle` opção para limpar estilos duplicados.

## Etapa 5: conte os estilos após a limpeza

Após fazer a limpeza, contaremos novamente o número de estilos para verificar se diminuiu. Use o código a seguir para exibir a nova contagem de estilos:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Esta instrução exibe o número de estilos restantes após a limpeza.

### Exemplo de código-fonte para Cleanup Duplicate Style usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Contagem de estilos antes da limpeza.
	Console.WriteLine(doc.Styles.Count);

	// Limpa estilos duplicados do documento.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// contagem de estilos após a limpeza foi reduzida.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```