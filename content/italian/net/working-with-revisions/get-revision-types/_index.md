---
title: Ottieni tipi di parole di revisione
linktitle: Ottieni tipi di parole di revisione
second_title: Aspose.Words API di elaborazione dei documenti
description: Ottieni i tipi di revisione delle parole in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/get-revision-types/
---

In questa guida passo passo, ti spiegheremo come ottenere i tipi di revisioni delle parole in un documento di Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passaggio 2: scorrere i paragrafi

Successivamente, esamineremo i paragrafi del documento e verificheremo i tipi di revisioni delle parole associate a ciascun paragrafo.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Esempio di codice sorgente per ottenere tipi di revisione utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per ottenere i tipi di revisione in un documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i tipi di revisioni delle parole in un documento di Word utilizzando Aspose.Words per .NET. Abbiamo seguito i passaggi per caricare il documento, esaminare i paragrafi e controllare i tipi di recensioni di parole associate a ciascun paragrafo. Ora puoi applicare questa conoscenza per analizzare le recensioni di parole nei tuoi documenti Word utilizzando Aspose.Words per .NET.

### Domande frequenti per ottenere i tipi di revisione delle parole

#### D: Come caricare un documento in Aspose.Words per .NET?

 R: Usa il`Document` classe di Aspose.Words per .NET per caricare un documento da un file. È possibile specificare il percorso completo del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### D: Come faccio a scorrere i paragrafi in un documento in Aspose.Words per .NET?

 R: Usa il`Paragraphs` proprietà della sezione del documento per ottenere la raccolta di paragrafi. È quindi possibile utilizzare un ciclo per scorrere ogni paragrafo.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Elabora ogni paragrafo qui
}
```

#### D: Come verificare se un paragrafo è stato spostato (cancellato) in Aspose.Words per .NET?

 A: Usa un paragrafo`IsMoveFromRevision` proprietà per verificare se è stata spostata (eliminata).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Il paragrafo è stato spostato (eliminato)
}
```

#### D: Come verificare se un paragrafo è stato spostato (inserito) in Aspose.Words per .NET?

 A: Usa un paragrafo`IsMoveToRevision`proprietà per verificare se è stata spostata (inserita).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Il paragrafo è stato spostato (inserito)
}
```