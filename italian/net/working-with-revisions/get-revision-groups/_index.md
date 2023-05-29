---
title: Ottieni gruppi di revisione
linktitle: Ottieni gruppi di revisione
second_title: Riferimento all'API Aspose.Words per .NET
description: Ottieni gruppi di revisione in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/get-revision-groups/
---

In questa guida passo passo, ti spiegheremo come ottenere i gruppi di revisione in un documento di Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passaggio 2: sfoglia i gruppi di revisione

Successivamente, passeremo in rassegna i gruppi di revisione presenti nel documento e ne mostreremo i dettagli, come autore, tipo di revisione e testo rivisto.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Codice sorgente di esempio per ottenere gruppi di revisione utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per ottenere i gruppi di revisione in un documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```


