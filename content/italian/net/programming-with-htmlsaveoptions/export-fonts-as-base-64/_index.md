---
title: Esporta caratteri come Base 64
linktitle: Esporta caratteri come Base 64
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per esportare i caratteri Base 64 durante il salvataggio di un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per esportare i caratteri base 64 con Aspose.Words per .NET. Questa funzione consente di esportare i caratteri come dati Base 64 quando si salva un documento in formato HTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio caricheremo il documento da esportare. Utilizzare il codice seguente per caricare il documento da una directory specificata:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Questo codice crea un'istanza di`Document` caricando il documento dalla directory specificata.

## Passaggio 3: configurazione delle opzioni di backup HTML

Ora configureremo le opzioni di salvataggio HTML per esportare i caratteri base 64. Utilizza il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Questo codice crea un'istanza di`HtmlSaveOptions` e imposta`ExportFontsAsBase64` A`true` per specificare che i caratteri devono essere esportati come dati base 64 durante il salvataggio come HTML.

## Passaggio 4: convertire e salvare il documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML configurate in precedenza. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Questo codice converte il documento in HTML e lo salva in un file con i caratteri esportati come dati base 64.

### Codice sorgente di esempio per esportare caratteri come Base 64 utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.

Ora hai imparato come esportare i caratteri base 64 quando salvi un documento come HTML utilizzando Aspose.Words per .NET. Seguendo la guida passo passo fornita in questo tutorial, puoi esportare facilmente i caratteri in modo sicuro e incorporarli nei tuoi documenti HTML.