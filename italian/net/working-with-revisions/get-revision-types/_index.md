---
title: Ottieni tipi di revisione
linktitle: Ottieni tipi di revisione
second_title: Riferimento all'API Aspose.Words per .NET
description: Ottieni i tipi di revisione in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/get-revision-types/
---

In questa guida passo passo, ti spiegheremo come ottenere i tipi di revisioni in un documento di Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passaggio 2: scorrere i paragrafi

Successivamente, esamineremo i paragrafi del documento e verificheremo i tipi di revisioni associati a ciascun paragrafo.

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
