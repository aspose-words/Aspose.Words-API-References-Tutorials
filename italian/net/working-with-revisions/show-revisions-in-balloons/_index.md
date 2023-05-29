---
title: Mostra le revisioni nei fumetti
linktitle: Mostra le revisioni nei fumetti
second_title: Riferimento all'API Aspose.Words per .NET
description: Mostra le revisioni nei fumetti con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/show-revisions-in-balloons/
---

In questa guida dettagliata, ti mostreremo come mostrare le revisioni nei fumetti in un documento Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passaggio 2: configurare le opzioni di visualizzazione della recensione

Configureremo le opzioni di visualizzazione per rendere visibili le revisioni nei fumetti.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Passaggio 3: salvare il documento in formato PDF

Infine, salveremo il documento come PDF con le revisioni mostrate nei fumetti.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Formati di output Markdown

L'output può essere formattato in markdown per migliorare la leggibilità. Per esempio :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Esempio di codice sorgente per Show Revisions In Balloons utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per mostrare le revisioni nei fumetti in un documento utilizzando Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Renderizza l'inserimento delle revisioni in linea, elimina e formatta le revisioni nei fumetti.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Visualizza le barre di revisione sul lato destro di una pagina.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```



