---
title: Ottieni i dettagli del gruppo di revisione
linktitle: Ottieni i dettagli del gruppo di revisione
second_title: Riferimento all'API Aspose.Words per .NET
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

