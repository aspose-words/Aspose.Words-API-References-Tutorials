---
title: Imposta il colore del controllo del contenuto
linktitle: Imposta il colore del controllo del contenuto
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare il colore di un controllo contenuto in un documento Word utilizzando Aspose.Words per .NET, personalizzandone l'aspetto.
type: docs
weight: 10
url: /it/net/programming-with-sdt/set-content-control-color/
---

Questo tutorial spiega come impostare il colore di un controllo contenuto in un documento di Word utilizzando Aspose.Words per .NET. Puoi personalizzare l'aspetto dei controlli contenuto modificandone il colore.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e recuperare il controllo del contenuto
 Caricare il documento Word utilizzando il file`Document` costruttore, passando il percorso del documento come parametro. Recuperare il controllo del contenuto desiderato dal documento. In questo esempio presupponiamo che il controllo del contenuto sia il primo tag di documento strutturato nel documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Passaggio 3: imposta il colore di controllo del contenuto
 Imposta il colore del controllo del contenuto assegnando a`Color` valore al`Color` proprietà del tag del documento strutturato. In questo esempio impostiamo il colore sul rosso.

```csharp
sdt.Color = Color.Red;
```

## Passaggio 4: salva il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Codice sorgente di esempio per Imposta colore controllo contenuto utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Questo è tutto! Hai impostato correttamente il colore di un controllo contenuto nel tuo documento Word utilizzando Aspose.Words per .NET.