---
title: Pulisci lo stile duplicato
linktitle: Pulisci lo stile duplicato
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per ripulire gli stili duplicati in un documento utilizzando Aspose.Words per .NET. Codice sorgente completo incluso.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

In questo tutorial ti guideremo passo passo attraverso il codice sorgente C# per ripulire gli stili duplicati con Aspose.Words per .NET. Questa funzione aiuta a rimuovere gli stili duplicati da un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio caricheremo il documento Word che vogliamo pulire. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: contare gli stili prima della pulizia

Prima di procedere con la pulizia conteremo il numero di stili presenti nel documento. Utilizzare il codice seguente per visualizzare il conteggio degli stili:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Questa istruzione mostra il numero di stili presenti nel documento.

## Passaggio 4: ripulisci gli stili duplicati

Ora puliamo gli stili duplicati dal documento. Utilizzare il codice seguente per eseguire la pulizia:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Questo codice ripulisce gli stili duplicati dal documento utilizzando le opzioni specificate. In questo esempio, abbiamo abilitato il file`DuplicateStyle` opzione per ripulire gli stili duplicati.

## Passaggio 5: contare gli stili dopo la pulizia

Dopo aver effettuato la pulizia, conteremo nuovamente il numero di stili per verificare se è diminuito. Utilizzare il codice seguente per visualizzare il conteggio dei nuovi stili:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Questa affermazione mostra il numero di stili rimanenti dopo la pulizia.

### Codice sorgente di esempio per la pulizia dello stile duplicato utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Conteggio degli stili prima della pulizia.
	Console.WriteLine(doc.Styles.Count);

	// Elimina gli stili duplicati dal documento.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Il conteggio degli stili dopo la pulizia è stato ridotto.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```