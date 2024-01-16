---
title: Carregar dicionário de hifenização para idioma
linktitle: Carregar dicionário de hifenização para idioma
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como carregar um dicionário de hifenização para um idioma específico em Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

Neste tutorial passo a passo, mostraremos como carregar um dicionário de hifenização para um idioma específico no Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Se ainda não o fez, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Passo 1: Carregando o documento

Primeiro, carregue seu documento do diretório especificado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Passo 2: Carregando o dicionário de hifenização

Em seguida, abra um fluxo no arquivo do dicionário de hifenização e salve-o no idioma desejado. Neste exemplo, carregamos um dicionário para alemão suíço (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Certifique-se de ter o arquivo de dicionário apropriado em seu diretório de dados.

## Etapa 3: salve o documento modificado

Por fim, salve o documento modificado:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Então ! Você carregou com sucesso um dicionário de hifenização para um idioma específico no Aspose.Words for .NET.

### Exemplo de código-fonte para carregamento de dicionário de hifenização para um idioma usando Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo para atender às suas necessidades específicas.

### Perguntas frequentes

#### P: Como carregar um dicionário de silabização para um idioma específico no Aspose.Words?

 R: Para carregar um dicionário de silabização para um idioma específico no Aspose.Words, você pode usar o`Hyphenation` classe e o`LoadDictionary()` método. Crie uma instância do`Hyphenation` aula e ligue para o`LoadDictionary()` método que especifica o caminho para o arquivo do dicionário de silabização para o idioma desejado. Isso carregará o dicionário de silabização em Aspose.Words.

#### P: Onde posso encontrar arquivos de dicionário de silabização para diferentes idiomas?

R: Você pode encontrar arquivos de dicionário de silabização para diferentes idiomas em vários recursos online. Esses arquivos geralmente estão no formato XML ou TEX. Você pode encontrar dicionários de silabização de código aberto para diferentes idiomas em sites dedicados a projetos linguísticos ou repositórios de código-fonte.

#### P: Como posso aplicar o dicionário silábico carregado a um documento no Aspose.Words?

 R: Para aplicar o dicionário de silabização carregado a um documento no Aspose.Words, você precisa iterar sobre as palavras do documento e usar o`Hyphenate()` método do`Hyphenation`classe para obter a silabização das palavras. Você pode então formatar as palavras silabizadas conforme necessário, por exemplo, adicionando hífens entre as sílabas.

#### P: Quais idiomas são suportados para silabização em Aspose.Words?

R: Aspose.Words suporta silabização para vários idiomas, incluindo inglês, francês, espanhol, alemão, italiano, holandês, russo, português, sueco, norueguês, dinamarquês, finlandês, polonês, tcheco e muitos mais. Verifique a documentação do Aspose.Words para obter a lista completa de idiomas suportados para silabização.