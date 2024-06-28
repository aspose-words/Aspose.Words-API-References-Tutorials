---
title: Ignorar texto dentro de excluir revisões
linktitle: Ignorar texto dentro de excluir revisões
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar o recurso "Ignorar texto dentro de exclusão de revisões" do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar o recurso "Ignorar texto dentro de excluir revisões" na biblioteca Aspose.Words for .NET. Este recurso é útil quando queremos ignorar o texto dentro das revisões de exclusão durante o processamento de palavras com documentos.

## Visão geral da biblioteca Aspose.Words for .NET

Antes de mergulhar nos detalhes do código, deixe-me apresentar brevemente a biblioteca Aspose.Words for .NET. É uma poderosa biblioteca que permite criar, modificar e converter documentos Word em aplicações .NET. Ele oferece muitos recursos avançados para processamento de texto com documentos, incluindo gerenciamento de revisões.

## Compreendendo o recurso "Ignorar texto dentro de exclusão de revisões"

recurso "Ignorar texto dentro de revisões de exclusão" em Aspose.Words for .NET permite especificar se o texto dentro de revisões de exclusão deve ser ignorado durante certas operações, como localizar e substituir texto. Quando este recurso está habilitado, o texto excluído nas revisões não é considerado durante as operações.

## Etapa 1: Criando um novo documento usando Aspose.Words for .NET

 Antes de começarmos a manipular o texto em um documento, precisamos criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto:

```csharp
Document doc = new Document();
```

## Etapa 2: Inserir texto não revisado no documento

 Assim que tivermos um documento, podemos inserir texto não revisado usando um`DocumentBuilder` objeto. Por exemplo, para inserir o texto “Texto Excluído”, podemos usar o`Writeln` e`Write` métodos:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Etapa 3: remover um parágrafo com revisões de rastreamento

Para ilustrar o uso do recurso "Ignorar texto dentro de exclusão de revisões", excluiremos um parágrafo do documento usando o rastreamento de revisão. Isso nos permitirá ver como esse recurso afeta as operações subsequentes.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Etapa 4: aplicar o recurso "Ignorar texto dentro de exclusão de revisões"

 Agora que preparamos nosso documento excluindo um parágrafo, podemos ativar o recurso "Ignorar texto dentro de excluir revisões" usando um`FindReplaceOptions` objeto. Vamos definir o`IgnoreDeleted`propriedade para`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Etapa 5: usando expressões regulares para localizar e substituir

Para realizar operações de busca e substituição no texto do documento, utilizaremos expressões regulares. No nosso exemplo, procuraremos todas as ocorrências da letra “e” e as substituiremos por um asterisco “* ". .LÍQUIDO`Regex` classe é usada para isso:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Etapa 6: Exibindo a saída do documento modificado

 Após aplicar a pesquisa e substituição, podemos exibir o conteúdo alterado do documento usando o`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

## Etapa 7: Modificando as opções para incluir texto excluído

 Se quisermos incluir o texto excluído no resultado de saída, podemos alterar as opções para não ignorar o texto excluído. Para isso vamos definir o`IgnoreDeleted`propriedade para`false`:

```csharp
options. IgnoreDeleted = false;
```

## Etapa 8: saída do documento modificado com texto excluído

Após alterar as opções, podemos realizar a busca e substituir novamente para obter o resultado com o texto excluído incluído:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Exemplo de código-fonte para Ignore Text Inside Delete Revisions usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar o uso do recurso "Ignorar texto dentro de excluir revisões" com Aspose.Words for .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insira texto não revisado.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Remova o primeiro parágrafo com revisões de rastreamento.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar o recurso "Ignorar texto dentro de excluir revisões" no Aspose.Words for .NET. Este recurso é útil para ignorar texto dentro de revisões de exclusão ao manipular documentos. Seguimos um guia passo a passo para criar um documento, inserir texto, excluir um parágrafo com rastreamento de revisão, aplicar o recurso “Ignorar texto dentro, excluir revisões” e realizar operações de localização e substituição.

### Perguntas frequentes

#### P: O que é a função "Ignorar texto dentro de exclusão de revisões" no Aspose.Words for .NET?

R: A função "Ignorar texto dentro de revisões de exclusão" em Aspose.Words for .NET permite que você especifique se o texto dentro de revisões de exclusão deve ser ignorado durante certas operações, como localizar e substituir texto. Quando este recurso está habilitado, o texto excluído nas revisões não é considerado durante as operações.

#### P: O que é Aspose.Words para .NET?

R: Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e converter documentos do Word em aplicativos .NET. Ele oferece muitos recursos avançados para processamento de texto com documentos, incluindo gerenciamento de revisões.

#### P: Como criar um novo documento no Aspose.Words for .NET?

 R: Antes de começar a manipular o texto em um documento, você precisa criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto. Aqui está um exemplo de código para criar um novo documento:

```csharp
Document doc = new Document();
```

#### P: Como inserir texto não editado em um documento usando Aspose.Words for .NET?

 R: Depois de ter um documento, você pode inserir texto não revisado usando um`DocumentBuilder` objeto. Por exemplo, para inserir o texto "Texto Excluído", você pode usar o`Writeln` e`Write` métodos:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### P: Como excluo um parágrafo com rastreamento de revisão no Aspose.Words for .NET?

R: Para ilustrar o uso da função "Ignorar texto dentro de exclusão de revisões", excluiremos um parágrafo do documento usando o rastreamento de revisão. Isso nos permitirá ver como esta função afeta as operações subsequentes.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### P: Como ativar o recurso "Ignorar texto dentro de exclusão de revisões" no Aspose.Words for .NET?

 R: Agora que preparamos nosso documento excluindo um parágrafo, podemos ativar o recurso "Ignorar texto dentro de excluir revisões" usando um`FindReplaceOptions` objeto. Vamos definir o`IgnoreDeleted`propriedade para`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### P: Como pesquisar e substituir usando expressões regulares no Aspose.Words for .NET?

R: Para realizar operações de busca e substituição no texto do documento, usaremos expressões regulares. No nosso exemplo, procuraremos todas as ocorrências da letra “e” e as substituiremos por um asterisco “* ". Usaremos o .NET`Regex` aula para isso:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### P: Como visualizar o conteúdo alterado do documento no Aspose.Words for .NET?

R: Depois de aplicar a pesquisa e substituição, podemos exibir o conteúdo alterado do documento usando o`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

#### P: Como incluir texto excluído no resultado de saída em Aspose.Words for .NET?

 R: Se quisermos incluir o texto excluído no resultado de saída, podemos alterar as opções para não ignorar o texto excluído. Para isso, definiremos o`IgnoreDeleted`propriedade para`false`:

```csharp
options. IgnoreDeleted = false;
```

#### P: Como mostrar o documento editado com texto excluído no Aspose.Words for .NET?

R: Após alterar as opções, podemos fazer uma nova pesquisa e substituir para obter o resultado com o texto excluído incluído:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
