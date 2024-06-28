---
title: Criar marcador em documento do Word
linktitle: Criar marcador em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar marcadores em documentos do Word e especificar níveis de visualização de marcadores em um PDF usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/create-bookmark/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Criar marcador na biblioteca Aspose.Words for .NET. Este recurso permite criar marcadores em um documento e especificar níveis de visualização de marcadores em um arquivo PDF de saída.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando o Documento e o Gerador

 Antes de criar marcadores, precisamos criar um documento e um construtor de documentos usando o`Document` e`DocumentBuilder` objetos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passo 2: Criando o marcador principal

 Nós usamos o`StartBookmark` método para iniciar um marcador principal e o`EndBookmark` método para acabar com isso. Nesse meio tempo, podemos adicionar texto e outros marcadores:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Adicione mais marcadores ou texto aqui.

builder. EndBookmark("My Bookmark");
```

## Etapa 3: Criando marcadores aninhados

 Também podemos criar marcadores aninhados dentro de um marcador principal. Usamos o mesmo`StartBookmark` e`EndBookmark` métodos para criar e finalizar marcadores aninhados:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Etapa 4: Especificar os níveis de visualização dos marcadores no arquivo PDF de saída

 Nós usamos o`PdfSaveOptions` objeto para especificar os níveis de visualização do marcador no arquivo PDF de saída. Nós usamos o`BookmarksOutlineLevels` propriedade

  para adicionar marcadores principais e marcadores aninhados com seus respectivos níveis:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Exemplo de código-fonte para Criar marcador usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar a criação de marcadores usando Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Criar marcador do Aspose.Words for .NET. Seguimos um guia passo a passo para criar marcadores em um documento e especificar níveis de visualização de marcadores em um arquivo PDF de saída.

### Perguntas frequentes

#### P: Quais são os pré-requisitos para usar a função "Criar favoritos" no Aspose.Words for .NET?

R: Para usar a função "Criar favoritos" no Aspose.Words for .NET, você deve ter conhecimento básico da linguagem C#. Você também precisa de um ambiente de desenvolvimento .NET com a biblioteca Aspose.Words instalada.

#### P: Como criar um documento no Aspose.Words for .NET?

 R: Para criar um documento no Aspose.Words for .NET, você pode usar o`Document` aula. Aqui está um exemplo de código:

```csharp
Document doc = new Document();
```

#### P: Como criar um marcador mestre em um documento usando Aspose.Words for .NET?

 R: Para criar um marcador principal em um documento usando Aspose.Words for .NET, você pode usar o`StartBookmark` método para iniciar o marcador, adicionar texto ou outros marcadores dentro e use o` EndBookmark` para acabar com isso. Aqui está um exemplo de código:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### P: Como criar um marcador aninhado dentro de um marcador principal usando Aspose.Words for .NET?

 R: Para criar um marcador aninhado dentro de um marcador principal usando Aspose.Words for .NET, você pode usar o mesmo`StartBookmark` e`EndBookmark` métodos para iniciar e finalizar o marcador aninhado. Aqui está um exemplo de código:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### P: Como especificar os níveis de visualização dos marcadores em um PDF de saída usando Aspose.Words for .NET?

 R: Para especificar os níveis de visualização de marcadores em um PDF de saída usando Aspose.Words for .NET, você pode usar o`PdfSaveOptions` classe e o`BookmarksOutlineLevels` propriedade. Você pode adicionar marcadores principais e marcadores aninhados com seus respectivos níveis. Aqui está um exemplo de código:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### P: Como salvar um documento após criar marcadores usando Aspose.Words for .NET?

 R: Para salvar um documento após criar marcadores usando Aspose.Words for .NET, você pode usar o`Save` método do`Document` objeto especificando o caminho do arquivo de destino. Aqui está um exemplo de código:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### P: Como especificar os níveis de visualização dos marcadores em um PDF de saída usando Aspose.Words for .NET?

 R: Para especificar os níveis de visualização de marcadores em um PDF de saída usando Aspose.Words for .NET, você pode usar o`PdfSaveOptions` classe e o`BookmarksOutlineLevels` propriedade. Você pode adicionar marcadores principais e marcadores aninhados com seus respectivos níveis. Aqui está um exemplo de código:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### P: Como criar marcadores aninhados dentro de um marcador principal usando Aspose.Words for .NET?

 R: Para criar marcadores aninhados dentro de um marcador principal usando Aspose.Words for .NET, você pode usar o mesmo`StartBookmark` e`EndBookmark` métodos para iniciar e finalizar marcadores aninhados. Certifique-se de especificar o marcador pai como parâmetro ao chamar o`StartBookmark` método. Aqui está um exemplo de código:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### P: Como adicionar texto dentro de um marcador usando Aspose.Words for .NET?

 R: Para adicionar texto dentro de um marcador usando Aspose.Words for .NET, você pode usar o`Write` método do`DocumentBuilder`objeto especificando o texto a ser adicionado. Aqui está um exemplo de código:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### P: Como criar um marcador mestre em um documento usando Aspose.Words for .NET?

 R: Para criar um marcador principal em um documento usando Aspose.Words for .NET, você pode usar o`StartBookmark` método para iniciar o marcador e o`EndBookmark` método para acabar com isso. Aqui está um exemplo de código:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```