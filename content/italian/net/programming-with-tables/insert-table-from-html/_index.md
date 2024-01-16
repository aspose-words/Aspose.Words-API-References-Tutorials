---
title: Inserisci tabella da Html
linktitle: Inserisci tabella da Html
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire una tabella da HTML in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/insert-table-from-html/
---

In questo tutorial impareremo come inserire una tabella in un documento Word da HTML utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial sarai in grado di inserire tabelle da HTML nei tuoi documenti Word a livello di programmazione.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e inizializzazione del generatore di documenti
Per avviare l'elaborazione parole con il documento e il generatore di documenti, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti
Document doc = new Document();

// Inizializza il generatore di documenti
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 3: inserimento della tabella da HTML
Successivamente, inseriremo la tabella nel documento utilizzando il codice HTML. Utilizza il seguente codice:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Qui usiamo il`InsertHtml` metodo del generatore di documenti per inserire l'HTML contenente la tabella. L'HTML specificato crea una tabella con due righe e due celle in ciascuna riga. Puoi personalizzare il contenuto della tabella modificando il codice HTML in base alle tue esigenze.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella inserita da HTML. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per Inserisci tabella da Html utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Tieni presente che AutoFitSettings non si applica alle tabelle inserite da HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come inserire una tabella in un documento Word da HTML utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi inserire tabelle da HTML nei tuoi documenti Word a livello di codice. Questa funzionalità ti consente di convertire e importare dati tabulari da origini HTML nei tuoi documenti Word.
