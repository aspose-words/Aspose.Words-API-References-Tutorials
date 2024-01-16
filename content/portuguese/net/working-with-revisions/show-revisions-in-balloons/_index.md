---
title: Mostrar revisões em balões
linktitle: Mostrar revisões em balões
second_title: API de processamento de documentos Aspose.Words
description: Mostre revisões em balões com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/show-revisions-in-balloons/
---

Neste guia passo a passo, mostraremos como mostrar revisões em balões em um documento do Word usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Carregando o documento

O primeiro passo é fazer o upload do documento contendo as revisões.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Etapa 2: configurar opções de exibição de avaliações

Configuraremos as opções de exibição para tornar as revisões visíveis em balões.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Passo 3: Salve o documento em formato PDF

Por fim, salvaremos o documento como PDF com as revisões mostradas em balões.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Formatos de saída Markdown

A saída pode ser formatada em markdown para melhorar a legibilidade. Por exemplo :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Exemplo de código-fonte para Mostrar revisões em balões usando Aspose.Words for .NET

Aqui está o código-fonte completo para mostrar revisões em balões em um documento usando Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Renderiza inserções de revisões inline, exclusão e formatação de revisões em balões.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Renderiza barras de revisão no lado direito de uma página.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Conclusão

Neste tutorial, aprendemos como exibir revisões em balões em um documento do Word usando Aspose.Words for .NET. Usando as opções de exibição apropriadas, conseguimos tornar as revisões visíveis em bolhas com barras de revisão no lado direito. Aspose.Words for .NET oferece muitos recursos poderosos para manipular documentos do Word, incluindo gerenciamento de revisões. Agora você pode usar esse conhecimento para mostrar revisões em balões em seus próprios documentos do Word usando Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como fazer upload de um documento no Aspose.Words for .NET?

 R: Use o`Document` classe de Aspose.Words for .NET para carregar um documento de um arquivo. Você pode especificar o caminho completo do documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Como exibir revisões em balões com Aspose.Words for .NET?

 R: Use o`ShowInBalloons` propriedade do`RevisionOptions` objeto para configurar a exibição de revisões em balões. Você pode definir esta propriedade em`ShowInBalloons.FormatAndDelete` para mostrar revisões em balões com revisões de exclusão e formatação.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### P: Como salvar um documento em formato PDF com Aspose.Words for .NET?

 R: Use o`Save` método do`Document` objeto para salvar o documento em formato PDF. Você deve especificar o caminho de destino completo com a extensão ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```