---
title: Alterar o espaçamento e os recuos dos parágrafos asiáticos no documento do Word
linktitle: Alterar o espaçamento e os recuos dos parágrafos asiáticos no documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como alterar o espaçamento e recuos de parágrafos asiáticos em documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
Neste tutorial, orientaremos você sobre como alterar o espaçamento e os recuos de um parágrafo asiático usando Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e aplicar as alterações.

## Passo 1: Carregando o documento

Para começar, especifique o diretório dos seus documentos e carregue o documento que contém a tipografia asiática em um objeto Document. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Etapa 2: alterar o espaçamento e os recuos dos parágrafos

Modificaremos agora o espaçamento e os recuos do primeiro parágrafo do documento asiático. Veja como:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Atualizar ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Atualizar ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Atualizar ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Atualizar ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Atualizar ParagraphFormat.SpaceAfter
```

## Passo 3: Salvando o documento

 Após inserir o campo do formulário de entrada de texto, salve o documento no local desejado usando o`Save` método. Certifique-se de fornecer o caminho de arquivo apropriado:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Exemplo de código-fonte para alterar espaçamento e recuos de parágrafos asiáticos usando Aspose.Words para .NET

Aqui está o código-fonte completo para o recurso Editar espaçamento e recuos de parágrafos asiáticos com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent será atualizado
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent será atualizado
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent será atualizado
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore será atualizado
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter será atualizado

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Com este código você poderá alterar o espaçamento e os recuos de um parágrafo asiático usando Aspose.Words for .NET.

## Conclusão

 Neste tutorial, aprendemos como alterar o espaçamento e os recuos de um parágrafo asiático usando Aspose.Words for .NET. Ao modificar as propriedades relevantes do`ParagraphFormat`podemos controlar o layout e a aparência dos parágrafos asiáticos em um documento do Word. Este recurso é útil para personalizar a formatação de texto com caracteres asiáticos e obter a apresentação visual desejada em documentos com conteúdo de idiomas mistos.

### Perguntas frequentes

#### P: O que o recurso "Alterar espaçamento e recuos de parágrafos asiáticos" no Aspose.Words for .NET faz?

R: O recurso "Alterar espaçamento e recuos de parágrafos asiáticos" em Aspose.Words for .NET permite modificar as propriedades de espaçamento e recuo de um parágrafo asiático em um documento do Word. Você pode ajustar os recuos esquerdo e direito, recuo da primeira linha, espaço antes e espaço depois dos valores para controlar o layout e a aparência do parágrafo.

#### P: Como altero o espaçamento e os recuos de um parágrafo asiático usando Aspose.Words for .NET?

 R: Para alterar o espaçamento e os recuos de um parágrafo asiático, você precisa acessar o`ParagraphFormat`do parágrafo de destino e modificar suas propriedades relevantes. No código de exemplo fornecido, acessamos o primeiro parágrafo do documento e definimos o`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , e`LineUnitAfter` propriedades para ajustar o espaçamento e os recuos.

#### P: Posso aplicar essas alterações a outros parágrafos do documento?

 R: Sim, você pode aplicar essas alterações a outros parágrafos do documento acessando seus respectivos`ParagraphFormat` objetos. O código de exemplo tem como alvo o primeiro parágrafo do documento, mas você pode modificar outros parágrafos ajustando o índice no campo`Paragraphs` coleção ou usando outros critérios para selecionar os parágrafos desejados.