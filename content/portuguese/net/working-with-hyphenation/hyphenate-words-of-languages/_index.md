---
title: Hifenizar palavras de idiomas
linktitle: Hifenizar palavras de idiomas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como hifenizar palavras em diferentes idiomas em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-hyphenation/hyphenate-words-of-languages/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como hifenizar palavras em diferentes idiomas em documentos do Word usando Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Se ainda não o fez, baixe e instale a biblioteca do site oficial.

## Etapa 1: inicializando o objeto Documento

 Primeiro, inicialize o`Document` objeto especificando o caminho para o documento de origem que contém texto em diferentes idiomas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Etapa 2: salvando dicionários de hifenização

A seguir, salve os dicionários de hifenização para os diferentes idiomas que deseja processar. Neste exemplo, registramos dicionários para inglês americano e alemão suíço:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Certifique-se de ter os arquivos de dicionário apropriados em seu diretório de dados.

## Etapa 3: Processamento de palavras por hifenização

Agora você pode usar recursos de hifenização para processar palavras em diferentes idiomas. Você pode usar diferentes métodos de`Document` ou`DocumentBuilder` dependendo de suas necessidades específicas.

```csharp
// Exemplo: usando o método Hyphenate do DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Etapa 4: salve o documento

Por fim, salve o documento modificado:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Então ! Você processou palavras com sucesso hifenizando-as em diferentes idiomas em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para hifenização de palavras usando Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo para atender às suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso silabizar uma palavra em um idioma específico com Aspose.Words?

 R: Para silabizar uma palavra em um idioma específico com Aspose.Words, você pode usar o`Hyphenation` classe e o`Hyphenate()` método. Crie uma instância do`Hyphenation` classe especificando o idioma desejado e, em seguida, chame o`Hyphenate()` método passando a palavra para silabizar como argumento. Isto lhe dará as sílabas da palavra no idioma especificado.

#### P: Quais códigos de idioma devo usar para especificar o idioma de silabização em Aspose.Words?

R: Para especificar o idioma de silabização em Aspose.Words, você deve usar os códigos de idioma apropriados. Por exemplo, você pode usar "en" para inglês, "fr" para francês, "es" para espanhol, "de" para alemão, etc. Consulte a documentação do Aspose.Words para obter uma lista completa dos códigos de idiomas suportados.

#### P: A silabização funciona para todos os idiomas no Aspose.Words?

R: A silabização em Aspose.Words depende de regras de silabização específicas do idioma. Embora Aspose.Words suporte uma ampla variedade de idiomas, alguns idiomas podem não ser suportados ou a silabização pode não estar disponível para eles. Verifique a documentação do Aspose.Words para descobrir quais idiomas são suportados para silabização.