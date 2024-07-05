---
title: Metacaracteres no padrão de pesquisa
linktitle: Metacaracteres no padrão de pesquisa
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar metacaracteres no padrão de pesquisa com Aspose.Words for .NET para manipular documentos do Word.
type: docs
weight: 10
url: /pt/net/find-and-replace-text/meta-characters-in-search-pattern/
---
Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Meta Characters In Search Pattern na biblioteca Aspose.Words for .NET. Este recurso permite usar metacaracteres especiais para realizar pesquisas avançadas e substituições em documentos do Word.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando um Novo Documento

 Antes de começarmos a usar metacaracteres no padrão de pesquisa, precisamos criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Etapa 2: inserir texto no documento

 Assim que tivermos um documento, podemos inserir texto usando um`DocumentBuilder` objeto. Em nosso exemplo, usamos o`Writeln` e`Write` métodos para inserir duas linhas de texto:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Etapa 3: encontre e substitua texto por metacaracteres

 Agora usaremos o`Range.Replace` função para pesquisar e substituir texto usando um padrão de pesquisa contendo metacaracteres especiais. Em nosso exemplo, substituímos a frase "Esta é a linha 1&pEsta é a linha 2" por "Esta linha foi substituída" usando o`&p` metacaractere para representar uma quebra de parágrafo:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Passo 4: Inserindo uma quebra de página no documento

 Para ilustrar o uso de outro metacaractere, inseriremos uma quebra de página no documento usando o comando`InsertBreak` método com o`BreakType.PageBreak` parâmetro. Primeiro movemos o cursor do`DocumentBuilder` ao final do documento, inserimos a quebra de página e uma nova linha de texto:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Etapa 5: encontre e substitua por outro metacaractere

 Agora faremos outra pesquisa e substituição usando o`&m` metacaractere para representar uma quebra de página. Substituímos a frase "Esta é a linha 1 e mEsta é a linha 2" por "A quebra de página foi substituída por um novo texto". :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Passo 6: Salvando o documento editado

Finalmente, salvamos o documento modificado em um diretório especificado usando o`Save` método:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Exemplo de código-fonte para metacaracteres no padrão de pesquisa usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar o uso de metacaracteres no padrão de pesquisa com Aspose.Words for .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar metacaracteres no padrão de pesquisa do Aspose.Words for .NET. Seguimos um guia passo a passo para criar um documento, inserir texto, realizar pesquisas e substituir usando metacaracteres especiais, inserir quebras de página e salvar o documento editado.

### Perguntas frequentes

#### P: O que é o recurso Metacaracteres no padrão de pesquisa no Aspose.Words for .NET?

R: O recurso Metacaracteres no padrão de pesquisa do Aspose.Words for .NET permite que você use metacaracteres especiais para realizar pesquisas avançadas e substituições em documentos do Word. Esses metacaracteres permitem representar quebras de parágrafo, quebras de seção, quebras de página e outros elementos especiais em seu padrão de pesquisa.

#### P: Como criar um novo documento no Aspose.Words for .NET?

 R: Antes de usar metacaracteres no modelo de pesquisa, você deve criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto. Aqui está um exemplo de código para criar um novo documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### P: Como inserir texto em um documento usando Aspose.Words for .NET?

 R: Depois de ter um documento, você pode inserir texto usando um`DocumentBuilder` objeto. Em nosso exemplo, usamos o`Writeln` e`Write` métodos para inserir duas linhas de texto:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### P: Como pesquisar e substituir texto por metacaracteres em um documento usando Aspose.Words for .NET?

 R: Para pesquisar e substituir texto por metacaracteres, você pode usar o`Range.Replace` método. Em nosso exemplo, substituímos a frase "Esta é a linha 1&pEsta é a linha 2" por "Esta linha foi substituída" usando o`&p` metacaractere para representar uma quebra de parágrafo:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### P: Como inserir uma quebra de página em um documento usando Aspose.Words for .NET?

R: Para ilustrar o uso de outro metacaractere, inseriremos uma quebra de página no documento usando o`InsertBreak` método com o`BreakType.PageBreak` parâmetro. Primeiro movemos o cursor do`DocumentBuilder` ao final do documento, inserimos a quebra de página e uma nova linha de texto:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### P: Como pesquisar e substituir por outro metacaractere em um documento usando Aspose.Words for .NET?

 R: Agora realizaremos outra pesquisa e substituição usando o`&m` metacaractere para representar uma quebra de página. Substituímos a frase "Esta é a linha 1 e mEsta é a linha 2" por "A quebra de página foi substituída por um novo texto". :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### P: Como salvar o documento editado no Aspose.Words for .NET?

 R: Depois de fazer alterações no documento, você pode salvá-lo em um diretório especificado usando o`Save` método:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```