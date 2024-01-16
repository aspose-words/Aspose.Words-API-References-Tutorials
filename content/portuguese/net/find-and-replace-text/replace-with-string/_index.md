---
title: Substituir por string
linktitle: Substituir por string
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como substituir texto por uma string em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/find-and-replace-text/replace-with-string/
---
Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Replace With String na biblioteca Aspose.Words for .NET. Este recurso permite realizar a substituição de texto com base em uma sequência de caracteres específica em um documento do Word.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando um Novo Documento

 Antes de começarmos a usar a substituição de string, precisamos criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Etapa 2: inserir texto no documento

 Assim que tivermos um documento, podemos inserir texto usando um`DocumentBuilder` objeto. Em nosso exemplo, usamos o`Writeln` método para inserir a frase "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Etapa 3: substitua por uma string

 Nós usamos o`Range.Replace`método para substituir texto por uma string. Em nosso exemplo, substituímos todas as ocorrências da palavra “triste” por “ruim” usando o`FindReplaceOptions` opção com o`FindReplaceDirection.Forward` direção de pesquisa:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Passo 4: Salvando o documento editado

Finalmente, salvamos o documento modificado em um diretório especificado usando o`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Exemplo de código-fonte para Substituir por String usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para ilustrar o uso da substituição por uma string de caracteres com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Replace With String do Aspose.Words for .NET. Seguimos um passo a passo para criar um documento, inserir texto, substituir por uma string e salvar o documento modificado.

### Perguntas frequentes

#### P: Qual é a função "Replace With String" no Aspose.Words for .NET?

R: A função "Replace With String" no Aspose.Words for .NET permite que você execute a substituição de texto com base em uma sequência de caracteres específica em um documento do Word. Ele permite que você encontre ocorrências de uma string específica e substitua-as por outra string especificada.

#### P: Como posso criar um novo documento usando Aspose.Words for .NET?

 R: Para criar um novo documento usando Aspose.Words for .NET, você pode instanciar um`Document` objeto. Aqui está um exemplo de código C# para criar um novo documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### P: Como posso inserir texto em um documento usando Aspose.Words for .NET?

 R: Depois de ter um documento, você pode inserir texto usando um`DocumentBuilder` objeto. No Aspose.Words for .NET, você pode usar vários métodos de`DocumentBuilder` classe para inserir texto em locais diferentes. Por exemplo, você pode usar o`Writeln` método para inserir texto em uma nova linha. Aqui está um exemplo:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### P: Como posso realizar a substituição de texto por uma string no Aspose.Words for .NET?

 R: Para realizar a substituição de texto por uma string no Aspose.Words for .NET, você pode usar o`Range.Replace` método e especifique a string a ser substituída e a string pela qual substituí-la. Este método executa uma correspondência de texto simples e substitui todas as ocorrências da string especificada. Aqui está um exemplo:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### P: Posso realizar a substituição de texto com distinção entre maiúsculas e minúsculas com a função "Replace With String" no Aspose.Words for .NET?

R: Sim, por padrão, a função "Replace With String" no Aspose.Words for .NET diferencia maiúsculas de minúsculas. Isso significa que ele substituirá apenas o texto que corresponda exatamente à string especificada em termos de maiúsculas e minúsculas. Se desejar realizar uma substituição sem distinção entre maiúsculas e minúsculas, você pode modificar o texto a ser substituído e a sequência de substituição para ter o mesmo caso ou pode usar outras técnicas, como expressões regulares.

#### P: Posso substituir várias ocorrências de uma string em um documento usando a função "Replace With String" no Aspose.Words for .NET?

 R: Sim, você pode substituir várias ocorrências de uma string em um documento usando a função "Replace With String" em Aspose.Words for .NET. O`Range.Replace` O método substituirá todas as ocorrências da string especificada no conteúdo do documento.

#### P: Há alguma limitação ou consideração ao usar a função "Replace With String" no Aspose.Words for .NET?

R: Ao usar a função "Replace With String" no Aspose.Words for .NET, é importante estar ciente do contexto e garantir que a substituição seja aplicada somente onde pretendido. Certifique-se de que a sequência de pesquisa não apareça em locais indesejados, como dentro de outras palavras ou como parte de uma formatação especial. Além disso, considere as implicações de desempenho ao processar palavras com documentos grandes ou substituições frequentes.

#### P: Posso substituir strings por comprimentos diferentes usando a função "Replace With String" no Aspose.Words for .NET?

R: Sim, você pode substituir strings por comprimentos diferentes usando a função "Replace With String" em Aspose.Words for .NET. A string de substituição pode ter qualquer comprimento e substituirá a correspondência exata da string de pesquisa. O documento será ajustado de acordo para acomodar o novo comprimento da sequência.