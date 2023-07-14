---
title: Controllo del contenuto della casella combinata
linktitle: Controllo del contenuto della casella combinata
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come creare un controllo del contenuto della casella combinata in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/combo-box-content-control/
---

Questo tutorial spiega come creare un controllo del contenuto della casella combinata in un documento di Word utilizzando Aspose.Words per .NET. I controlli del contenuto della casella combinata consentono agli utenti di selezionare un elemento da un elenco a discesa.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e Word Processing con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si desidera salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento e un StructuredDocumentTag
 Crea una nuova istanza di`Document` classe e a`StructuredDocumentTag` per rappresentare il controllo del contenuto della casella combinata. Specificare`SdtType.ComboBox` come il tipo e`MarkupLevel.Block` come livello di markup per creare una casella combinata a livello di blocco.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Passaggio 3: aggiungi elementi alla casella combinata
 Aggiungere elementi alla casella combinata utilizzando il`ListItems`proprietà del`StructuredDocumentTag` Ogni elemento è rappresentato da un`SdtListItem` oggetto, che accetta un testo visualizzato e un valore. In questo esempio, aggiungiamo tre elementi alla casella combinata.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Passaggio 4: aggiungere lo StructuredDocumentTag al documento
 Aggiungere il controllo del contenuto della casella combinata al corpo del documento utilizzando il`AppendChild` metodo del corpo della prima sezione del documento.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Passaggio 5: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Codice sorgente di esempio per il controllo del contenuto della casella combinata utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Questo è tutto! Hai creato correttamente un controllo del contenuto della casella combinata nel documento di Word utilizzando Aspose.Words per .NET.