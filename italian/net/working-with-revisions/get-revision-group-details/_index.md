---
title: Ottieni i dettagli del gruppo di revisione
linktitle: Ottieni i dettagli del gruppo di revisione
second_title: Aspose.Words API di elaborazione dei documenti
description: Ottieni i dettagli del gruppo di revisione in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/get-revision-group-details/
---

In questa guida dettagliata, ti mostreremo come ottenere i dettagli di un gruppo di revisioni in un documento di Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passaggio 2: sfoglia le revisioni

Successivamente, passeremo in rassegna le revisioni presenti nel documento e ne mostreremo i dettagli, come il tipo, l'autore, la data e il testo rivisto.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Codice sorgente di esempio per ottenere i dettagli del gruppo di revisione utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per ottenere i dettagli di un gruppo di revisioni in un documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come ottenere i dettagli di un gruppo di revisioni in un documento di Word utilizzando Aspose.Words per .NET. Utilizzando un ciclo e le proprietà appropriate, siamo stati in grado di visualizzare dettagli come il tipo di revisione, l'autore, la data e il testo rivisto. Aspose.Words per .NET offre molte potenti funzionalità per la manipolazione di documenti Word, inclusa la gestione delle revisioni. Ora puoi utilizzare questa conoscenza per ottenere i dettagli del gruppo di revisione nei tuoi documenti Word utilizzando Aspose.Words per .NET.

### FAQ

#### D: Come faccio a caricare un documento con le revisioni in Aspose.Words per .NET?

 R: Usa il`Document`class di Aspose.Words per .NET per caricare un documento da un file contenente revisioni. È possibile specificare il percorso completo del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### D: Come ottengo i dettagli di un gruppo di revisione in Aspose.Words per .NET?

 R: Esamina le revisioni del documento utilizzando un ciclo e accedi alle proprietà di ogni revisione per ottenere i dettagli desiderati. Puoi usare il`RevisionType`, `Author`, `DateTime` E`ParentNode` properties per ottenere rispettivamente il tipo di revisione, l'autore, la data e il testo rivisto.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### D: Come verificare se una revisione appartiene a un gruppo in Aspose.Words per .NET?

 R: Usa il`Group`proprietà del`Revision` oggetto per verificare se una revisione appartiene a un gruppo. Se la`Group` la proprietà è`null`significa che la revisione non appartiene a nessun gruppo.

```csharp
if (revision.Group != null)
{
      // La revisione appartiene a un gruppo
}
else
{
      // La revisione non appartiene a nessun gruppo
}
```