---
title: Localizar e substituir texto simples no Word
linktitle: Localizar e substituir texto simples no Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como localizar e substituir um texto simples em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/find-and-replace-text/simple-find-replace/
---
Neste artigo, exploraremos o código-fonte C# acima para entender como usar o Simple Text Find And Replace no Word da biblioteca Aspose.Words for .NET. Este recurso permite realizar uma substituição simples de texto, pesquisando uma sequência específica de caracteres e substituindo-a por outra sequência de caracteres em um documento do Word.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando um Novo Documento

 Antes de começarmos a usar localizar e substituir simples, precisamos criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Etapa 2: inserir texto no documento

 Assim que tivermos um documento, podemos inserir texto usando um`DocumentBuilder` objeto. Em nosso exemplo, usamos o`Writeln` método para inserir a frase "Olá_CustomerName_",:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Etapa 3: substituição de texto simples

 Nós usamos o`Range.Replace` método para realizar a substituição simples de texto. Em nosso exemplo, substituímos todas as ocorrências da string "_ClientName_ " com "James Bond" usando o`FindReplaceOptions` opção com o`FindReplaceDirection.Forward` direção de pesquisa:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Passo 4: Salvando o documento editado

Finalmente, salvamos o documento modificado em um diretório especificado usando o`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Exemplo de código-fonte para Simple Find Replace usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar o uso de pesquisa simples e substituição por Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Salve o documento modificado
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Simple Find Replace do Aspose.Words for .NET. Seguimos um guia passo a passo para criar um documento, inserir texto, realizar uma substituição simples de texto e salvar o documento editado.

### Perguntas frequentes

#### P: O que é a função Localizar e Substituir Texto Simples no Aspose.Words for .NET?

R: O recurso Localizar e substituir texto simples no Aspose.Words for .NET permite que você execute a substituição simples de texto em um documento do Word. Ele permite que você pesquise uma sequência de caracteres específica e substitua-a por outra sequência de caracteres. Isto pode ser útil quando você deseja fazer alterações globais em um documento, como substituir nomes, datas ou outras informações.

#### P: Como criar um novo documento no Aspose.Words for .NET?

 R: Antes de usar a função Localizar e substituir texto simples, você deve criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto. Aqui está um exemplo de código para criar um novo documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### P: Como inserir texto em um documento usando Aspose.Words for .NET?

 R: Depois de ter um documento, você pode inserir texto usando um`DocumentBuilder` objeto. Em nosso exemplo, usamos o`Writeln` método para inserir a frase "Olá_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### P: Como executo a substituição simples de texto em um documento usando Aspose.Words for .NET?

 R: Para realizar uma substituição simples de texto, você pode usar o`Range.Replace` método. Em nosso exemplo, substituímos todas as ocorrências da string "_ClientName_ " com "James Bond" usando o`FindReplaceOptions` opção com o`FindReplaceDirection.Forward` direção de pesquisa:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### P: Como salvar o documento editado no Aspose.Words for .NET?

 R: Depois de fazer a substituição do texto, você pode salvar o documento modificado em um diretório especificado usando o`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```