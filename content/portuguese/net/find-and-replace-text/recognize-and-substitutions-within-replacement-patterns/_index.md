---
title: Reconhecer e substituir dentro dos padrões de substituição
linktitle: Reconhecer e substituir dentro dos padrões de substituição
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar padrões de substituição com reconhecimentos e substituições em Aspose.Words for .NET para manipular documentos do Word.
type: docs
weight: 10
url: /pt/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Reconhecer e substituir dentro dos padrões de substituição na biblioteca Aspose.Words para .NET. Esse recurso ajuda a reconhecer padrões de pesquisa complexos e a realizar substituições com base em grupos capturados durante a manipulação de documentos.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando um Novo Documento

Antes de começarmos a usar correspondências e substituições em padrões de substituição, precisamos criar um novo documento usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto:

```csharp
Document doc = new Document();
```

## Etapa 2: inserir texto no documento

 Assim que tivermos um documento, podemos inserir texto usando um`DocumentBuilder` objeto. Em nosso exemplo, estamos usando o`Write` método para inserir a frase "Jason dá algum dinheiro a Paul". :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Etapa 3: Reconhecimentos e Substituições em Padrões de Substituição

 Agora usaremos o`Range.Replace` função para realizar pesquisa e substituição de texto usando uma expressão regular para reconhecer padrões específicos. Em nosso exemplo, usamos a expressão regular`([A-z]+) gives money to ([A-z]+)` reconhecer frases em que alguém dá dinheiro a outra pessoa. Usamos o padrão de substituição`$2 takes money from $1` para realizar a substituição invertendo os papéis. O uso de`$1` e`$2` refere-se aos grupos capturados pela expressão regular:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Exemplo de código-fonte para reconhecimento e substituições dentro de padrões de substituição usando Aspose.Words para .NET

Aqui está o exemplo de código-fonte completo para ilustrar o uso de correspondências e substituições em padrões de substituição com Aspose.Words for .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar o recurso Reconhecer e substituir dentro dos padrões de substituição do Aspose.Words for .NET. Seguimos um guia passo a passo para criar um documento, inserir texto, realizar busca e substituição usando expressões regulares e padrões de substituição baseados em grupos capturados e manipular o documento.

### Perguntas frequentes

#### P: O que é o recurso "Reconhecer e substituir dentro dos padrões de substituição" no Aspose.Words for .NET?

R: O recurso "Reconhecer e substituições dentro de padrões de substituição" no Aspose.Words for .NET permite reconhecer padrões de pesquisa complexos usando expressões regulares e realizar substituições com base nos grupos capturados durante a manipulação do documento. Ele permite transformar o texto correspondente dinamicamente, referenciando os grupos capturados no padrão de substituição.

#### P: Como posso criar um novo documento usando Aspose.Words for .NET?

 R: Para criar um novo documento usando Aspose.Words for .NET, você pode instanciar um`Document` objeto. Aqui está um exemplo de código C# para criar um novo documento:

```csharp
Document doc = new Document();
```

#### P: Como posso inserir texto em um documento usando Aspose.Words for .NET?

 R: Depois de ter um documento, você pode inserir texto usando um`DocumentBuilder` objeto. Por exemplo, para inserir a frase “Jason dá dinheiro para Paul.”, você pode usar o`Write` método:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### P: Como posso realizar pesquisa e substituição de texto usando expressões regulares no Aspose.Words for .NET?

 R: Para realizar pesquisa e substituição de texto usando expressões regulares no Aspose.Words for .NET, você pode usar o`Range.Replace` função junto com um padrão de expressão regular. Você pode criar um`Regex` objeto com o padrão desejado e passe-o para o`Replace` método:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### P: Como posso usar grupos capturados no padrão de substituição durante a pesquisa de texto e substituição no Aspose.Words for .NET?

 R: Para usar grupos capturados no padrão de substituição durante a pesquisa e substituição de texto no Aspose.Words for .NET, você pode ativar o`UseSubstitutions` propriedade do`FindReplaceOptions` objeto. Isso permite que você faça referência aos grupos capturados usando`$1`, `$2`, etc. no padrão de substituição:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### P: O que o código-fonte de exemplo demonstra para o recurso "Reconhecer e substituir dentro dos padrões de substituição" no Aspose.Words for .NET?

R: O código-fonte de exemplo demonstra o uso do recurso "Reconhecer e substituir dentro dos padrões de substituição" no Aspose.Words for .NET. Ele mostra como criar um documento, inserir texto, realizar pesquisa e substituição de texto usando expressões regulares e usar grupos capturados no padrão de substituição para transformar dinamicamente o texto correspondente.

#### P: Onde posso encontrar mais informações e exemplos sobre o uso de expressões regulares no Aspose.Words for .NET?

R: Para obter mais informações e exemplos sobre o uso de expressões regulares no Aspose.Words for .NET, você pode consultar o[Referências de API Aspose.Words para .NET](https://reference.aspose.com/words/net/). A documentação fornece explicações detalhadas e exemplos de código para vários cenários envolvendo expressões regulares e manipulação de texto em Aspose.Words for .NET.

#### P: Posso manipular outros aspectos do documento com base nos grupos capturados durante a pesquisa e substituição de texto?

R: Sim, você pode manipular outros aspectos do documento com base nos grupos capturados durante a pesquisa e substituição de texto. Além de realizar substituições de texto, você pode modificar a formatação, estilos, estrutura do documento e outros elementos com base nos grupos capturados usando as diversas APIs fornecidas pelo Aspose.Words for .NET.

#### P: Há alguma limitação ou consideração ao usar expressões regulares e grupos capturados no Aspose.Words for .NET?

R: Embora expressões regulares e grupos capturados ofereçam recursos poderosos para pesquisa e substituição de texto no Aspose.Words for .NET, é importante considerar a complexidade e as implicações de desempenho. Expressões regulares altamente complexas e um grande número de grupos capturados podem afetar o desempenho. É recomendado testar e otimizar expressões regulares para seus casos de uso específicos para garantir uma manipulação eficiente de documentos.

#### P: Posso usar o recurso "Reconhecer e substituir dentro dos padrões de substituição" com outros idiomas além do inglês?

R: Sim, o recurso "Reconhecer e substituir dentro dos padrões de substituição" no Aspose.Words for .NET pode ser usado com outros idiomas além do inglês. Expressões regulares são independentes de linguagem e podem ser criadas para corresponder a padrões específicos em qualquer linguagem. Você pode ajustar o padrão de expressão regular para se adequar ao idioma desejado e aos padrões de texto específicos que deseja reconhecer e substituir.