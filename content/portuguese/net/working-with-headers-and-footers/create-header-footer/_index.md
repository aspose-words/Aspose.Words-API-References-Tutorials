---
title: Criar rodapé de cabeçalho
linktitle: Criar rodapé de cabeçalho
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar cabeçalhos e rodapés em seus documentos do Word com Aspose.Words for .NET. Personalize cabeçalhos e rodapés para cada página.
type: docs
weight: 10
url: /pt/net/working-with-headers-and-footers/create-header-footer/
---

Aqui está um guia passo a passo para explicar o seguinte código-fonte C# para criar cabeçalhos e rodapés usando a funcionalidade Aspose.Words for .NET. Certifique-se de incluir a biblioteca Aspose.Words em seu projeto antes de usar este código.

## Etapa 1: definir o caminho do diretório do documento

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Certifique-se de especificar o caminho correto para o diretório de documentos onde o documento editado será salvo.

## Passo 2: Crie um documento e um gerador de documentos

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aqui criamos uma instância do`Document` classe e uma instância do`DocumentBuilder` classe que nos permitirá manipular o documento e adicionar elementos.

## Etapa 3: definir os parâmetros da página e o primeiro cabeçalho

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Especifique se queremos que os cabeçalhos/rodapés da primeira página sejam diferentes das outras páginas.
// Você também pode usar a propriedade PageSetup.OddAndEvenPagesHeaderFooter para especificar
// cabeçalhos/rodapés diferentes para páginas pares e ímpares.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Definimos os parâmetros da página, incluindo a distância do cabeçalho, e depois passamos para o cabeçalho principal (`HeaderPrimary`). Usamos o gerador de documentos para adicionar texto e formatar o cabeçalho.

## Etapa 4: insira uma imagem e texto no cabeçalho principal

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Usamos o gerador de documentos para inserir uma imagem no canto superior esquerdo do cabeçalho principal e, em seguida, adicionamos algum texto alinhado à direita.

## Passo 5: Insira uma tabela no rodapé principal

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Etapa 6: adicione uma nova página e defina cabeçalhos/rodapés

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Esta seção não precisa de um cabeçalho/rodapé diferente para a primeira página, precisamos apenas de uma página de título no documento,
// o cabeçalho/rodapé desta página já foi definido na seção anterior.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Esta seção exibe os cabeçalhos/rodapés da seção anterior por padrão, chame currentSection.HeadersFooters.LinkToPrevious(false) para quebrar este link,
// a largura da página é diferente para a nova seção, portanto, precisamos definir larguras de célula diferentes para uma tabela de rodapé.
currentSection.HeadersFooters.LinkToPrevious(false);

// Se quisermos usar os cabeçalhos/rodapés já existentes para esta seção,
//mas com algumas pequenas alterações, pode fazer sentido copiar os cabeçalhos/rodapés
// da seção anterior e aplicar as alterações necessárias onde quisermos.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Salve o documento
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Adicionamos uma quebra de página e uma quebra de seção para criar uma nova página onde os cabeçalhos/rodapés primários ficarão visíveis. Definimos os parâmetros para a nova seção, então usamos o`CopyHeadersFootersFromPreviousSection` método para copiar os cabeçalhos/rodapés da seção anterior. Por fim, definimos as larguras de célula apropriadas para a tabela de rodapé principal e salvamos o documento.

### Exemplo de código-fonte para criar cabeçalhos e rodapés com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Especifique se queremos que os cabeçalhos/rodapés da primeira página sejam diferentes das outras páginas.
// Você também pode usar a propriedade PageSetup.OddAndEvenPagesHeaderFooter para especificar
// cabeçalhos/rodapés diferentes para páginas pares e ímpares.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Insira uma imagem posicionada no canto superior/esquerdo do cabeçalho.
// A distância das bordas superior/esquerda da página é definida em 10 pontos.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Usamos uma tabela com duas células para fazer uma parte do texto na linha (com numeração de páginas).
// Alinhar à esquerda e a outra parte do texto (com direitos autorais) alinhar à direita.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Ele usa os campos PAGE e NUMPAGES para calcular automaticamente o número da página atual e muitas páginas.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// Faça uma quebra de página para criar uma segunda página na qual os cabeçalhos/rodapés primários serão vistos.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Esta seção não precisa de um cabeçalho/rodapé de primeira página diferente, precisamos apenas de uma página de título no documento,
// o cabeçalho/rodapé desta página já foi definido na seção anterior.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Esta seção exibe cabeçalhos/rodapés da seção anterior
// por padrão, chame currentSection.HeadersFooters.LinkToPrevious(false) para cancelar a largura desta página
// é diferente para a nova seção e, portanto, precisamos definir larguras de células diferentes para uma tabela de rodapé.
currentSection.HeadersFooters.LinkToPrevious(false);

// Se quisermos usar o conjunto de cabeçalho/rodapé já existente para esta seção.
// Mas com algumas pequenas modificações, pode ser conveniente copiar cabeçalhos/rodapés
// da seção anterior e aplicar as modificações necessárias onde quisermos.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### Perguntas frequentes

#### P: Como posso adicionar um cabeçalho ao meu documento no Aspose.Words?

 R: Para adicionar um cabeçalho ao seu documento no Aspose.Words, você pode usar o`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` método. Este método adiciona um título principal à primeira seção do documento.

#### P: Como posso adicionar um rodapé ao meu documento no Aspose.Words?

 R: Para adicionar um rodapé ao seu documento no Aspose.Words, você pode usar o`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`método. Este método adiciona um rodapé primário à primeira seção do documento.

#### P: Como posso adicionar texto ao meu cabeçalho ou rodapé no Aspose.Words?

 R: Para adicionar texto ao seu cabeçalho ou rodapé no Aspose.Words, você pode usar o`HeaderFooter.Paragraphs` propriedade para obter a coleção de parágrafos do cabeçalho ou rodapé e, em seguida, adicione um parágrafo contendo seu texto a esta coleção usando o`ParagraphCollection.Add` método.

#### P: Posso personalizar o conteúdo do cabeçalho ou rodapé com imagens e números de página no Aspose.Words?

 R: Sim, você pode personalizar o conteúdo do cabeçalho ou rodapé com imagens e números de página no Aspose.Words. Você pode usar objetos como`Shape` para adicionar imagens e objetos como`Field` para adicionar números de página ao cabeçalho ou rodapé.

#### P: Posso alterar a fonte, o tamanho e a cor do texto no meu cabeçalho ou rodapé no Aspose.Words?

 R: Sim, você pode alterar a fonte, o tamanho e a cor do texto no cabeçalho ou rodapé no Aspose.Words. Você pode acessar propriedades de formatação de texto, como`Font` para alterar a fonte,`Size` para ajustar o tamanho e`Color`para definir a cor do texto.