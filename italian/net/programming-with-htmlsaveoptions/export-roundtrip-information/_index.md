---
title: Esporta informazioni di andata e ritorno
linktitle: Esporta informazioni di andata e ritorno
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per esportare le informazioni di andata e ritorno durante il salvataggio di un documento come HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per esportare informazioni di andata e ritorno da un documento con Aspose.Words per .NET. Questa funzione consente di includere informazioni di andata e ritorno nel file HTML esportato, semplificando il recupero delle modifiche apportate al documento originale.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento da esportare. Utilizzare il codice seguente per caricare il documento da una directory specificata:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Questo codice crea un'istanza di`Document` caricando il documento dalla directory specificata.

## Passaggio 3: configurazione delle opzioni di backup HTML

Ora configureremo le opzioni di salvataggio HTML per esportare le informazioni di andata e ritorno del documento. Usa il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Questo codice crea un'istanza di`HtmlSaveOptions` imposta il`ExportRoundtripInformation` opzione a`true` per includere le informazioni di andata e ritorno durante l'esportazione.

## Passaggio 4: conversione e salvataggio del documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML configurate in precedenza. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Questo codice converte il documento in HTML, incluse le informazioni di andata e ritorno, e salva il file HTML esportato nella directory specificata.

### Codice sorgente di esempio per l'esportazione di informazioni di andata e ritorno utilizzando Aspose.Words per .NET


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.