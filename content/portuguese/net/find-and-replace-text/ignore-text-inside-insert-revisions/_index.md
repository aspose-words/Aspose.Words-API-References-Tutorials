---
title: Ignorar revisões de inserção de texto dentro
linktitle: Ignorar revisões de inserção de texto dentro
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar o recurso "Ignorar texto dentro de revisões de inserção" do Aspose.Words for .NET para manipular revisões de inserção em documentos do Word.
type: docs
weight: 10
url: /pt/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Ignore Text Inside Insert Revisions na biblioteca Aspose.Words for .NET. Este recurso é útil quando queremos ignorar texto dentro de revisões de inserção enquanto manipulamos documentos.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando um Novo Documento

 Antes de começarmos a manipular o texto dentro das revisões de inserção, precisamos criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto:

```csharp
Document doc = new Document();
```

## Etapa 2: inserir texto com rastreamento de revisão

 Assim que tivermos um documento, podemos inserir texto com rastreamento de revisão usando um`DocumentBuilder`objeto. Por exemplo, para inserir o texto "Inserido" com acompanhamento de revisão, podemos usar o`StartTrackRevisions`, `Writeln` e`StopTrackRevisions` métodos:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Etapa 3: insira texto não revisado

 Além do texto com controle de revisão, também podemos inserir texto não revisado usando o`DocumentBuilder` objeto. Por exemplo, para inserir o texto “Texto” sem revisão, podemos utilizar o`Write` método:

```csharp
builder.Write("Text");
```

## Etapa 4: usando a função Ignorar texto dentro de inserir revisões

 Para ignorar o texto dentro das revisões de inserção nas operações subsequentes, podemos usar um`FindReplaceOptions` objeto e definir o`IgnoreInserted`propriedade para`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Etapa 5: usando expressões regulares para pesquisar e substituir

Para realizar operações de busca e substituição no texto do documento, utilizaremos expressões regulares. No nosso exemplo, procuraremos todas as ocorrências da letra “e” e as substituiremos por um asterisco “* ". Usaremos .NET`Regex` aula para isso:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Etapa 6: Visualizando a saída do documento modificado

 Após aplicar a pesquisa e substituição, podemos exibir o conteúdo alterado do documento usando o`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

## Etapa 7: Alterando opções para incluir revisões de inserção

Se quisermos incluir o texto dentro das revisões de inserção no resultado de saída, podemos alterar as opções para não ignorar as revisões de inserção. Para isso vamos definir o`IgnoreInserted`propriedade para`false`:

```csharp
options.IgnoreInserted = false;
```

## Etapa 8: Visualizando o Documento Modificado com Inserir Revisões

Após alterar as opções, podemos realizar a busca e substituir novamente para obter o resultado com o texto dentro das revisões de inserção incluídas:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Exemplo de código-fonte para Ignorar revisões de inserção de texto usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar o uso da função Ignore Text Inside Insert Revisions com Aspose.Words for .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insira texto com revisões de rastreamento.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Insira texto não revisado.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Ignore Text Inside Insert Revisions em Aspose.Words for .NET. Seguimos um guia passo a passo para criar um documento, inserir texto com rastreamento de revisões e texto não revisado, usando a função Ignore Text Inside Insert Revisions, realizando operações de pesquisa e substituição por expressões regulares e exibindo o documento modificado.

### Perguntas frequentes

#### P: O que é o recurso "Ignorar texto dentro de revisões de inserção" no Aspose.Words for .NET?

R: O recurso "Ignorar texto dentro das revisões de inserção" no Aspose.Words for .NET permite especificar se o texto dentro das revisões de inserção deve ser ignorado durante certas operações, como localizar e substituir texto. Quando este recurso está habilitado, o texto dentro das revisões inseridas não é considerado durante as operações.

#### P: Como posso criar um novo documento usando Aspose.Words for .NET?

 R: Para criar um novo documento usando Aspose.Words for .NET, você pode instanciar um`Document` objeto. Aqui está um exemplo de código C# para criar um novo documento:

```csharp
Document doc = new Document();
```

#### P: Como posso inserir texto com rastreamento de revisão no Aspose.Words for .NET?

R: Depois de ter um documento, você pode inserir texto com controle de revisão usando um`DocumentBuilder` objeto. Por exemplo, para inserir o texto "Inserido" com controle de revisão, você pode usar o`StartTrackRevisions`, `Writeln` , e`StopTrackRevisions` métodos:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### P: Como posso inserir texto não revisado no Aspose.Words for .NET?

 R: Além do texto com controle de revisão, você também pode inserir texto não revisado usando o`DocumentBuilder` objeto. Por exemplo, para inserir o texto "Texto" sem revisão, você pode usar o`Write` método:

```csharp
builder.Write("Text");
```

#### P: Como posso ignorar o texto dentro das revisões de inserção no Aspose.Words for .NET?

 R: Para ignorar o texto dentro das revisões de inserção durante as operações subsequentes, você pode usar um`FindReplaceOptions` objeto e definir o`IgnoreInserted`propriedade para`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### P: Como posso pesquisar e substituir usando expressões regulares no Aspose.Words for .NET?

 R: Para realizar operações de pesquisa e substituição no texto do documento usando expressões regulares, você pode usar o .NET`Regex` aula. Por exemplo, para pesquisar todas as ocorrências da letra “e” e substituí-las por um asterisco “* ", você pode criar um`Regex` objeto e usá-lo com o`Replace` método:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### P: Como posso visualizar a saída modificada do documento no Aspose.Words for .NET?

 R: Depois de aplicar as operações de pesquisa e substituição, você pode visualizar o conteúdo alterado do documento usando o botão`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

#### P: Como posso incluir as revisões de inserção no resultado de saída no Aspose.Words for .NET?

 R: Para incluir o texto dentro das revisões de inserção no resultado de saída, você pode alterar as opções para não ignorar as revisões de inserção. Para isso, você pode definir o`IgnoreInserted` propriedade do`FindReplaceOptions` opor-se a`false`:

```csharp
options.IgnoreInserted = false;
```

#### P: Como posso exibir o documento modificado com as revisões de inserção no Aspose.Words for .NET?

R: Após alterar as opções para incluir revisões de inserção, você pode realizar a busca e substituir novamente para obter o resultado com o texto dentro das revisões de inserção incluídas:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```