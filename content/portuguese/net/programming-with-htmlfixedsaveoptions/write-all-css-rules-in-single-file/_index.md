---
title: Escreva todas as regras CSS em um único arquivo
linktitle: Escreva todas as regras CSS em um único arquivo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter um documento do Word em HTML fixo escrevendo todas as regras CSS em um único arquivo com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Ao converter um documento do Word em HTML fixo em um aplicativo C#, você pode querer consolidar todas as regras CSS em um único arquivo para melhor organização e portabilidade. Com a biblioteca Aspose.Words para .NET, você pode especificar facilmente essa funcionalidade usando as opções de salvamento HtmlFixedSaveOptions. Neste guia passo a passo, orientaremos você sobre como usar o código-fonte Aspose.Words para .NET C# para converter um documento do Word em HTML fixo, escrevendo todas as regras CSS em um único arquivo usando as opções de salvamento HtmlFixedSaveOptions.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca poderosa para criar, editar, converter e proteger documentos do Word em diferentes plataformas, incluindo .NET. Oferece diversos recursos para manipulação de documentos, como inserção de texto, alteração de formatação, adição de seções e muito mais.

## Carregando o documento do Word

O primeiro passo é carregar o documento Word que deseja converter para HTML fixo. Use a classe Document para carregar o documento do arquivo de origem. Aqui está um exemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Neste exemplo, carregamos o documento “Document.docx” localizado no diretório de documentos.

## Configurando opções de backup

A próxima etapa é configurar as opções de salvamento para conversão para HTML fixo. Use a classe HtmlFixedSaveOptions e defina a propriedade SaveFontFaceCssSeparately como false para gravar todas as regras CSS em um único arquivo. Veja como fazer isso:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Criamos um novo objeto HtmlFixedSaveOptions e definimos a propriedade SaveFontFaceCssSeparately como false para escrever todas as regras CSS em um único arquivo.

## Conversão de documento HTML corrigida

Agora que configuramos as opções de salvamento, podemos prosseguir com a conversão do documento para HTML fixo. Use o método Save da classe Document para salvar o documento convertido em formato HTML fixo especificando opções de salvamento. Aqui está um exemplo :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

Neste exemplo, salvamos o documento convertido como "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" usando as opções de salvamento especificadas.

### Exemplo de código-fonte para HtmlFixedSaveOptions com recurso "Escrever todas as regras CSS em um arquivo" usando Aspose.Words for .NET

```csharp
// Caminho de acesso ao seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento do Word
Document doc = new Document(dataDir + "Document.docx");

// Configure opções de backup com o recurso "Gravar todas as regras CSS em um arquivo"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Converter documento em HTML fixo
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Conclusão

Neste guia, abordamos como converter um documento do Word em HTML fixo, escrevendo todas as regras CSS em um único arquivo usando HtmlFixedSaveOptions com a biblioteca Aspose.Words para .NET. Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode aplicar facilmente essa funcionalidade em seu aplicativo C#. Escrever todas as regras CSS em um único arquivo facilita a organização e o gerenciamento do código HTML gerado durante a conversão do documento.