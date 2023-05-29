---
title: Accedi alla versione rivista
linktitle: Accedi alla versione rivista
second_title: Riferimento all'API Aspose.Words per .NET
description: Accedi a una versione rivista di un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/access-revised-version/
---

In questa guida dettagliata, ti mostreremo come accedere alla versione rivista di un documento Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Passaggio 2: accedere alla versione rivista

Passiamo ora alla versione riveduta del documento.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Passaggio 3: sfoglia le revisioni

Successivamente, passeremo in rassegna le revisioni presenti nel documento e visualizzeremo informazioni specifiche per i paragrafi che sono voci di elenco.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Esempio di codice sorgente per Access Revised Version utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per accedere alla versione rivista di un documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Passa alla versione rivista del documento.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```


