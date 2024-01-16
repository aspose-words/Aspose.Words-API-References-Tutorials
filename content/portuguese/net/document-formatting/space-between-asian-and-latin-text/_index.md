---
title: Espaço entre texto asiático e latino em documento do Word
linktitle: Espaço entre texto asiático e latino em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ajustar automaticamente o espaço entre texto asiático e latino em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-formatting/space-between-asian-and-latin-text/
---
Neste tutorial, mostraremos como usar o recurso Espaço entre texto asiático e latino no recurso de documento do Word com Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e aplicar as alterações.

## Passo 1: Criando e configurando o documento

Para começar, crie um novo documento e um objeto DocumentBuilder associado. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: Configurando o espaço entre o texto asiático e latino

Vamos agora configurar o espaço entre o texto asiático e latino usando as propriedades do objeto ParagraphFormat. Veja como:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Passo 3: Salvando o documento

 Após inserir o campo do formulário de entrada de texto, salve o documento no local desejado usando o`Save` método. Certifique-se de fornecer o caminho de arquivo apropriado:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Exemplo de código-fonte para espaço entre texto asiático e latino usando Aspose.Words para .NET

Aqui está o código-fonte completo do recurso Espaço entre texto asiático e latino com Aspose.Words for .NET:


```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

Com este código você poderá ajustar automaticamente o espaço entre o texto asiático e latino em seu documento usando Aspose.Words for .NET.

## Conclusão

Neste tutorial, exploramos o processo de uso do recurso Espaço para ajustar o espaçamento entre texto asiático e latino em um documento do Word com Aspose.Words for .NET. Seguindo as etapas descritas, você pode garantir espaçamento e alinhamento adequados, o que é particularmente útil ao lidar com conteúdo misto asiático e latino.

### Perguntas frequentes

#### P: Qual é o recurso Espaço entre texto asiático e latino em um documento do Word?

R: O recurso Espaço entre texto asiático e latino em um documento do Word refere-se à capacidade de ajustar automaticamente o espaçamento entre texto escrito em escritas diferentes, como asiática (por exemplo, chinês, japonês) e latina (por exemplo, inglês).

#### P: Por que é importante ajustar o espaço entre os textos asiáticos e latinos?

R: Ajustar o espaço entre os textos asiáticos e latinos é crucial para garantir que diferentes escritas se misturem harmoniosamente no documento. O espaçamento adequado melhora a legibilidade e a aparência visual geral, evitando que o texto pareça muito apertado ou espalhado.

#### P: Posso personalizar os ajustes de espaço entre diferentes scripts?

 R: Sim, você pode personalizar os ajustes de espaço entre diferentes scripts usando o`AddSpaceBetweenFarEastAndAlpha` e`AddSpaceBetweenFarEastAndDigit` propriedades. Ao ativar ou desativar essas propriedades, você pode controlar o espaço entre texto asiático e latino, bem como entre texto asiático e números.

#### P: O Aspose.Words for .NET oferece suporte a outros recursos de formatação de documentos?

R: Sim, Aspose.Words for .NET oferece amplo suporte para vários recursos de formatação de documentos. Inclui funcionalidades para estilos de fonte, parágrafos, tabelas, imagens e muito mais. Você pode manipular e formatar efetivamente seus documentos do Word de maneira programática.

#### P: Onde posso encontrar recursos e documentação adicionais para Aspose.Words for .NET?

 R: Para obter recursos abrangentes e documentação sobre o uso do Aspose.Words for .NET, visite[Referência da API Aspose.Words](https://reference.aspose.com/words/net/). Lá, você encontrará guias detalhados, tutoriais, exemplos de código e referências de API para ajudá-lo a utilizar com eficácia os poderosos recursos do Aspose.Words for .NET.