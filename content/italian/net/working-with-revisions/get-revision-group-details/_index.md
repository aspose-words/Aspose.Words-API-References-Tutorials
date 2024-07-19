---
title: Ottieni i dettagli del gruppo di revisione
linktitle: Ottieni i dettagli del gruppo di revisione
second_title: API di elaborazione dei documenti Aspose.Words
description: Ottieni i dettagli del gruppo di revisione in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/get-revision-group-details/
---

In questa guida passo passo, ti mostreremo come ottenere i dettagli di un gruppo di revisioni in un documento Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output di markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passaggio 2: sfoglia le revisioni

Successivamente, esamineremo le revisioni presenti nel documento e ne visualizzeremo i dettagli, come tipo, autore, data e testo rivisto.

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


### Codice sorgente di esempio per ottenere dettagli sul gruppo di revisione utilizzando Aspose.Words per .NET

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

In questo tutorial, abbiamo imparato come ottenere i dettagli di un gruppo di revisioni in un documento Word utilizzando Aspose.Words per .NET. Utilizzando un loop e le proprietà appropriate, siamo stati in grado di visualizzare dettagli come tipo di revisione, autore, data e testo rivisto. Aspose.Words per .NET offre molte potenti funzionalità per la manipolazione di documenti Word, inclusa la gestione delle revisioni. Ora puoi utilizzare questa conoscenza per ottenere i dettagli del gruppo di revisione nei tuoi documenti Word utilizzando Aspose.Words per .NET.

### Domande frequenti

#### D: Come carico un documento con revisioni in Aspose.Words per .NET?

 R: Usa il`Document` classe di Aspose.Words per .NET per caricare un documento da un file contenente revisioni. È possibile specificare il percorso completo del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### D: Come posso ottenere i dettagli di un gruppo di revisione in Aspose.Words per .NET?

R: Passa attraverso le revisioni del documento utilizzando un loop e accedi alle proprietà di ciascuna revisione per ottenere i dettagli desiderati. Puoi usare il`RevisionType`, `Author`, `DateTime`E`ParentNode` proprietà per ottenere rispettivamente il tipo di revisione, l'autore, la data e il testo rivisto.

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

 R: Usa il`Group` proprietà del`Revision` oggetto per verificare se una revisione appartiene a un gruppo. Se la`Group` la proprietà è`null`, significa che la revisione non appartiene a nessun gruppo.

```csharp
if (revision.Group != null)
{
      // La revisione appartiene ad un gruppo
}
else
{
      // La revisione non appartiene ad alcun gruppo
}
```