---
title: Ottieni gruppi di revisione
linktitle: Ottieni gruppi di revisione
second_title: Aspose.Words API di elaborazione dei documenti
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

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i gruppi di revisione in un documento di Word utilizzando Aspose.Words per .NET. Abbiamo seguito i passaggi per caricare il documento e sfogliare i gruppi di revisione, visualizzando dettagli come autore e tipo di recensione. Ora puoi applicare questa conoscenza per analizzare le revisioni del tuo documento Word utilizzando Aspose.Words per .NET.

### FAQ

#### D: Come caricare un documento in Aspose.Words per .NET?

 R: Usa il`Document` classe di Aspose.Words per .NET per caricare un documento da un file. È possibile specificare il percorso completo del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### D: Come sfogliare i gruppi di revisione in un documento in Aspose.Words per .NET?

 R: Usa il`Groups` proprietà del documento`Revisions` oggetto per ottenere la raccolta di gruppi di revisione. È quindi possibile utilizzare un ciclo per scorrere ogni gruppo di revisione.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Elabora ogni gruppo di revisione qui
}
```

#### D: Come ottenere l'autore di un gruppo di revisione in Aspose.Words per .NET?

 R: Usa il`Author`proprietà del`RevisionGroup` oggetto per ottenere l'autore del gruppo di revisione.

```csharp
string author = group.Author;
```

#### D: Come ottenere il tipo di revisione di un gruppo di revisione in Aspose.Words per .NET?

 R: Usa il`RevisionType`proprietà del`RevisionGroup`oggetto per ottenere il tipo di revisione del gruppo.

```csharp
string revisionType = group.RevisionType;
```