---
title: Aggancia alla griglia
linktitle: Aggancia alla griglia
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida passo passo per spiegare il codice sorgente C# della funzione Snap to Grid con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/snap-to-grid/
---

In questo tutorial, ti illustreremo come utilizzare la funzione Snap to Grid con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: creazione e configurazione del documento

Per iniziare, crea un nuovo documento e un oggetto DocumentBuilder associato. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: allineamento della griglia

Ora applicheremo l'allineamento della griglia a un paragrafo specifico e al carattere utilizzato nel paragrafo. Ecco come:

```csharp
// Abilita l'allineamento della griglia per il paragrafo
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Scrivi il testo nel paragrafo
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Abilita l'allineamento della griglia per il carattere utilizzato nel paragrafo
par.Runs[0].Font.SnapToGrid = true;
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Codice sorgente di esempio per Snap To Grid utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Snap to Grid con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Ottimizza il layout quando digiti i caratteri asiatici.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

Con questo codice sarai in grado di allineare il tuo testo alla griglia e ottimizzare l'aspetto del tuo documento usando Aspose.Words per .NET.

