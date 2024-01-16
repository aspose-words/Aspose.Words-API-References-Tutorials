---
title: Obtenha espaçamento entre linhas de fonte
linktitle: Obtenha espaçamento entre linhas de fonte
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como obter o espaçamento entre linhas de fonte em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/get-font-line-spacing/
---
Neste tutorial, mostraremos como obter o espaçamento entre linhas da fonte em um documento do Word usando a biblioteca Aspose.Words para .NET. O espaçamento entre linhas da fonte define o espaço vertical entre as linhas do texto. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto

## Etapa 1: Crie um novo documento e gerador de documentos
 Primeiro, criaremos um novo documento instanciando o`Document` classe e um construtor de documentos instanciando o`DocumentBuilder` aula.

```csharp
// Crie um novo documento
Document doc = new Document();

//Crie um gerador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: configurar a fonte
 A seguir, configuraremos a fonte definindo o`Name` propriedade do gerador de documentos.

```csharp
// Configurar a fonte
builder.Font.Name = "Calibri";
```

## Etapa 3: adicione texto ao documento
Agora usaremos o gerador de documentos para adicionar texto formatado ao documento.

```csharp
// Adicione texto ao documento
builder. Writen("qText");
```

## Etapa 4: obter espaçamento entre linhas de fonte
 Agora acessaremos o`Font` objeto do primeiro parágrafo do documento e recuperar o valor do`LineSpacing` propriedade.

```csharp
// Obtenha o espaçamento entre linhas da fonte
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Exemplo de código-fonte para obter espaçamento entre linhas de fonte usando Aspose.Words for .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusão
Neste tutorial, vimos como obter o espaçamento entre linhas da fonte em um documento do Word com Aspose.Words for .NET. O espaçamento entre linhas da fonte é importante para controlar o espaçamento vertical entre as linhas do texto. Sinta-se à vontade para usar esse recurso para personalizar a aparência do texto nos documentos.

### Perguntas frequentes

#### P: Como posso alterar o espaçamento entre linhas de um texto específico em um documento do Word?

R: Com Aspose.Words, você pode alterar facilmente o espaçamento entre linhas de um texto específico em um documento do Word. Use a API para selecionar o texto desejado e ajustar o espaçamento entre as linhas especificando o valor apropriado.

#### P: É possível aplicar espaçamento exato entre linhas em um documento Word?

R: Sim, Aspose.Words permite aplicar espaçamento exato entre linhas em um documento do Word. Você pode especificar um valor preciso para o espaçamento entre linhas usando a API.

#### P: Como posso ajustar o espaçamento entre linhas de todo o documento do Word?

R: Com Aspose.Words, você pode ajustar facilmente o espaçamento entre linhas de todo o documento do Word. Use os métodos fornecidos pela API para especificar o espaçamento entre linhas desejado para todo o documento.

#### P: O Aspose.Words oferece suporte a vários espaçamentos entre linhas?

R: Sim, Aspose.Words oferece suporte a vários espaçamentos entre linhas em documentos do Word. Você pode definir espaçamentos múltiplos, como 1,5 vezes ou 2 vezes o espaçamento normal, para as linhas do seu texto.

#### P: Como posso evitar problemas de sobreposição de linhas ao ajustar o espaçamento entre linhas?

R: Para evitar problemas de sobreposição de linhas ao ajustar o espaçamento entre linhas, certifique-se de escolher valores de espaçamento apropriados. Teste também a renderização final do seu documento para garantir que o texto permaneça legível e bem formatado.