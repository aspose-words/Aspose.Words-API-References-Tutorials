---
title: Recursos de tipo aberto
linktitle: Recursos de tipo aberto
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como habilitar e usar recursos Open Type no Aspose.Words for .NET
type: docs
weight: 10
url: /pt/net/enable-opentype-features/open-type-features/
---

Neste tutorial abrangente, você aprenderá como habilitar e utilizar recursos Open Type no Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você será capaz de trabalhar com recursos Open Type em seus documentos do Word.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: carregue o documento
Para começar, carregue o documento usando a classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Etapa 2: ativar recursos de tipo aberto
Para ativar os recursos Open Type, defina a propriedade TextShaperFactory da classe LayoutOptions como uma instância da fábrica do modelador de texto desejada. Neste exemplo, usamos HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Etapa 3: salve o documento
Depois de ativar os recursos Open Type, salve o documento no formato de saída desejado, como PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Exemplo de código-fonte para recursos de tipo aberto usando Aspose.Words para .NET
Aqui está o código-fonte completo para usar os recursos Open Type no Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como habilitar e utilizar recursos Open Type em Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode trabalhar com recursos Open Type em seus documentos do Word.

Os recursos Open Type oferecem recursos aprimorados de tipografia e modelagem de texto, permitindo criar documentos visualmente atraentes e com aparência profissional. Experimente diferentes fábricas de modeladores de texto e explore as possibilidades dos recursos Open Type em seus projetos.

### Perguntas frequentes

#### P: Como habilito os recursos OpenType no Aspose.Words for .NET?

R: Para habilitar recursos OpenType no Aspose.Words for .NET, você precisa seguir as etapas mencionadas no tutorial.

#### P: Quais recursos OpenType são suportados no Aspose.Words for .NET?

R: Aspose.Words for .NET oferece suporte a vários recursos OpenType, como ligaduras, variações de glifos, substituições contextuais e muito mais.

#### P: Como posso verificar se um recurso OpenType é compatível com uma fonte específica?

R: Você pode verificar se um recurso OpenType é compatível com uma fonte específica usando o`Font.OpenTypeFeatures` método em Aspose.Words para .NET.

#### P: Quais outros recursos de formatação de texto o Aspose.Words for .NET suporta?

R: Além dos recursos OpenType, Aspose.Words for .NET também oferece suporte a outros recursos de formatação de texto, como formatação de parágrafos, criação de tabelas, adição de imagens, etc.

#### P: Posso usar recursos OpenType em todas as versões do Aspose.Words for .NET?

R: Os recursos OpenType são suportados em versões mais recentes do Aspose.Words for .NET. Certifique-se de usar uma versão compatível para se beneficiar desses recursos.