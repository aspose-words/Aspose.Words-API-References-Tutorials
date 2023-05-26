---
title: Esporta font come base 64
linktitle: Esporta font come base 64
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo passo per esportare i caratteri base 64 durante il salvataggio di un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per esportare i font base 64 con Aspose.Words per .NET. Questa funzione consente di esportare i caratteri come dati base 64 durante il salvataggio di un documento in formato HTML.

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

Ora configureremo le opzioni di salvataggio HTML per esportare i caratteri base 64. Usa il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Questo codice crea un'istanza di`HtmlSaveOptions` e set`ExportFontsAsBase64` A`true` per specificare che i caratteri devono essere esportati come dati base 64 durante il salvataggio come HTML.

## Passaggio 4: conversione e salvataggio del documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML configurate in precedenza. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Questo codice converte il documento in HTML e lo salva in un file con i caratteri esportati come dati base 64.

### Esempio di codice sorgente per Export Fonts As Base 64 utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.

Ora hai imparato come esportare i caratteri base 64 quando salvi un documento come HTML usando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente esportare i font in modo sicuro e incorporarli nei tuoi documenti HTML.