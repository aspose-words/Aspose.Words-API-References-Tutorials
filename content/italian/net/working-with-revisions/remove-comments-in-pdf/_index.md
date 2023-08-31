---
title: Rimuovi commenti nel file PDF
linktitle: Rimuovi commenti nel file PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Rimuovi i commenti in un file PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/remove-comments-in-pdf/
---

In questa guida passo passo, ti spiegheremo come rimuovere i commenti in un file PDF utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output di markdown.

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

## Formati di output ribassati

L'output può essere formattato in markdown per migliorare la leggibilità. Per esempio :

```markdown
- Comments are hidden in the generated PDF.
```

### Codice sorgente di esempio per Rimuovi commenti in Pdf utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per rimuovere i commenti in un file PDF utilizzando Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Nascondi i commenti nel PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Conclusione

In questo tutorial, abbiamo imparato come rimuovere commenti da un file PDF utilizzando Aspose.Words per .NET. Utilizzando le opzioni di layout appropriate, siamo riusciti a nascondere i commenti durante la generazione del PDF. Aspose.Words per .NET offre una grande flessibilità per manipolare file Word e convertirli in diversi formati, incluso PDF. Ora puoi applicare questa conoscenza per rimuovere i commenti nei tuoi file PDF utilizzando Aspose.Words per .NET.

### Domande frequenti per rimuovere i commenti nel file PDF

#### D: Come caricare un documento in Aspose.Words per .NET?

 R: Usa il`Document` classe di Aspose.Words per .NET per caricare un documento da un file. È possibile specificare il percorso completo del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### D: Come nascondere i commenti nel PDF generato con Aspose.Words per .NET?

 R: Usa il`CommentDisplayMode` proprietà del`LayoutOptions` oggetto per configurare la modalità di visualizzazione dei commenti durante la generazione del PDF. Per nascondere i commenti, imposta questa proprietà su`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### D: Come salvare un documento come PDF con Aspose.Words per .NET?

 R: Usa il`Save` metodo del`Document` oggetto per salvare il documento in formato PDF. Specificare il percorso completo del file PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```