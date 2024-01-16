---
title: Grupo de quebra de linha de tipografia asiática em documento do Word
linktitle: Grupo de quebra de linha de tipografia asiática em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar o grupo de quebra de linha de tipografia asiática em documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-formatting/asian-typography-line-break-group/
---
Neste tutorial, mostraremos como usar o grupo de quebra de linha de tipografia asiática no recurso de documento do Word com Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e aplicar alterações de formatação.

## Passo 1: Carregando o documento

Para começar, especifique o diretório dos seus documentos e carregue o documento que contém a tipografia asiática em um objeto Document. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Etapa 2: configuração da tipografia asiática

Iremos agora definir as configurações de tipografia asiática para o primeiro parágrafo do documento. Veja como:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Passo 3: Salvando o documento

 Após inserir o campo do formulário de entrada de texto, salve o documento no local desejado usando o`Save` método. Certifique-se de fornecer o caminho de arquivo apropriado:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Exemplo de código-fonte para grupo de quebra de linha de tipografia asiática usando Aspose.Words para .NET

Aqui está o código-fonte completo do recurso Asian Typography Line Break Group com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Com este código você poderá aplicar o grupo de quebra de linha da tipografia asiática usando Aspose.Words for .NET.

## Conclusão

 Neste tutorial, exploramos o recurso "Grupo de quebra de linha de tipografia asiática" no Aspose.Words for .NET. Ao configurar o`FarEastLineBreakControl`, `WordWrap` , e`HangingPunctuation` propriedades do`ParagraphFormat`, conseguimos controlar o comportamento de quebra de linha da tipografia asiática em um documento do Word. Este recurso é útil para lidar com caracteres asiáticos e garantir quebras de linha e quebras de linha adequadas em documentos com conteúdo de idiomas mistos.

### Perguntas frequentes

#### P: O que é o recurso "Grupo de quebra de linha de tipografia asiática" no Aspose.Words for .NET?

R: O recurso "Grupo de quebra de linha de tipografia asiática" no Aspose.Words for .NET permite controlar o comportamento de quebra de linha para tipografia asiática em um documento do Word. Especificamente, afeta como as linhas são quebradas e quebradas ao lidar com caracteres asiáticos em parágrafos.

#### P: Como habilito o "Grupo de quebra de linha de tipografia asiática" no Aspose.Words for .NET?

 R: Para ativar o "Grupo de quebra de linha de tipografia asiática", você precisa configurar o`FarEastLineBreakControl`, `WordWrap` , e`HangingPunctuation` propriedades do`ParagraphFormat` para o(s) parágrafo(s) relevante(s) em seu documento. Contexto`FarEastLineBreakControl` para`false` garante que os caracteres asiáticos sejam tratados de forma semelhante aos caracteres latinos em relação à quebra de linha.`WordWrap` definido como`true` permite quebra automática de texto para tipografia asiática e`HangingPunctuation` definido como`false` evita que a pontuação fique pendurada no texto asiático.

#### P: Posso aplicar o "Grupo de quebra de linha de tipografia asiática" a parágrafos específicos de um documento?

R: Sim, você pode aplicar as configurações de “Grupo de quebra de linha de tipografia asiática” a parágrafos específicos em um documento do Word. No código de exemplo, as configurações são aplicadas ao primeiro parágrafo do documento. Você pode ajustar o código para direcionar outros parágrafos conforme necessário, acessando-os através do`Paragraphs` coleção da(s) seção(ões) relevante(s) no documento.