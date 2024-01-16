---
title: Ignorar texto dentro dos campos
linktitle: Ignorar texto dentro dos campos
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar o recurso "Ignorar texto dentro dos campos" do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/find-and-replace-text/ignore-text-inside-fields/
---
Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Ignore Text Inside Fields na biblioteca Aspose.Words for .NET. Este recurso é útil quando queremos ignorar o texto dentro dos campos ao manipular documentos.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando um Novo Documento

 Antes de começarmos a manipular o texto dentro dos campos, precisamos criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto:

```csharp
Document doc = new Document();
```

## Passo 2: Inserindo um campo com texto dentro

 Assim que tivermos um documento, podemos inserir um campo contendo texto dentro dele usando um`DocumentBuilder` objeto. Por exemplo, para inserir um campo "INCLUDETEXT" com o texto "Texto no campo", podemos utilizar o`InsertField` método:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## Etapa 3: usando a função Ignorar texto dentro dos campos

 Para ignorar o texto dentro dos campos em operações subsequentes, podemos usar um`FindReplaceOptions` objeto e definir o`IgnoreFields`propriedade para`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## Etapa 4: usando expressões regulares para pesquisar e substituir

Para realizar operações de busca e substituição no texto do documento, utilizaremos expressões regulares. No nosso exemplo, procuraremos todas as ocorrências da letra “e” e as substituiremos por um asterisco “* ". Usaremos .NET`Regex` aula para isso:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Etapa 5: Visualizando a saída do documento modificado

 Após aplicar a pesquisa e substituição, podemos exibir o conteúdo alterado do documento usando o`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

## Etapa 6: alterar opções para incluir campos

 incluímos o texto dentro dos campos no resultado de saída, podemos alterar as opções para não ignorar os campos. Para isso vamos definir o`IgnoreFields`propriedade para`false`:

```csharp
options.IgnoreFields = false;
```

## Passo 7: Exibindo o documento modificado com os campos

Após alterar as opções, podemos realizar a busca e substituir novamente para obter o resultado com o texto dentro dos campos incluídos:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Exemplo de código-fonte para Ignorar texto dentro de campos usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar o uso da função Ignore Text Inside Fields com Aspose.Words for .NET:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insira o campo com texto dentro.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Ignore Text Inside Fields em Aspose.Words for .NET. Seguimos um guia passo a passo para criar um documento, inserir um campo com texto dentro, usar a função Ignorar texto dentro dos campos, realizar operações de pesquisa e substituição por expressões regulares e exibir o documento modificado.

### Perguntas frequentes

#### P: O que é o recurso "Ignorar texto dentro dos campos" no Aspose.Words for .NET?

R: O recurso "Ignorar texto dentro dos campos" no Aspose.Words for .NET permite especificar se o texto dentro dos campos deve ser ignorado durante certas operações, como localizar e substituir texto. Quando este recurso está habilitado, o texto dentro dos campos não é considerado durante as operações.

#### P: Como posso criar um novo documento usando Aspose.Words for .NET?

 R: Para criar um novo documento usando Aspose.Words for .NET, você pode instanciar um`Document` objeto. Aqui está um exemplo de código C# para criar um novo documento:

```csharp
Document doc = new Document();
```

#### P: Como posso inserir um campo com texto dentro de um documento usando Aspose.Words for .NET?

 R: Depois de ter um documento, você pode inserir um campo com texto dentro dele usando um`DocumentBuilder` objeto. Por exemplo, para inserir um campo "INCLUDETEXT" com o texto "Texto no campo", você pode usar o`InsertField` método:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### P: Como posso ignorar o texto dentro dos campos no Aspose.Words for .NET?

 R: Para ignorar o texto dentro dos campos durante operações subsequentes, você pode usar um`FindReplaceOptions` objeto e definir o`IgnoreFields`propriedade para`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
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

#### P: Como posso incluir os campos no resultado de saída no Aspose.Words for .NET?

 R: Para incluir o texto dentro dos campos no resultado de saída, você pode alterar as opções para não ignorar os campos. Para isso, você pode definir o`IgnoreFields` propriedade do`FindReplaceOptions` opor-se a`false`:

```csharp
options.IgnoreFields = false;
```

#### P: Como posso exibir o documento modificado com os campos do Aspose.Words for .NET?

R: Após alterar as opções de inclusão de campos, você pode realizar a busca e substituir novamente para obter o resultado com o texto dentro dos campos incluídos:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```