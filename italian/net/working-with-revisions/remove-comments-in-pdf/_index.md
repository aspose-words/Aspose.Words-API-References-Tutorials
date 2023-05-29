---
title: Rimuovi commenti in pdf
linktitle: Rimuovi commenti in pdf
second_title: Riferimento all'API Aspose.Words per .NET
description: Rimuovi i commenti in un file PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/remove-comments-in-pdf/
---

In questa guida dettagliata, ti spiegheremo come rimuovere i commenti in un file PDF utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente i commenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passaggio 2: nascondi i commenti nel PDF

Configureremo l'opzione di layout per nascondere i commenti durante la generazione del PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Passaggio 3: salva il documento come PDF

Infine, salveremo il documento in formato PDF eliminando i commenti.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Formati di output Markdown

L'output può essere formattato in markdown per migliorare la leggibilità. Per esempio :

```markdown
- Comments are hidden in the generated PDF.
```

### Esempio di codice sorgente per Rimuovi commenti in Pdf utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per rimuovere i commenti in un file PDF utilizzando Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Nascondi i commenti nel PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```