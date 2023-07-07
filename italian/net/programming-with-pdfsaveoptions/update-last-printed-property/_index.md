---
title: Aggiorna l'ultima proprietà stampata nel documento PDF
linktitle: Aggiorna l'ultima proprietà stampata nel documento PDF
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo-passo per aggiornare la proprietà "Last Printed" durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Questo articolo fornisce una guida dettagliata su come utilizzare la proprietà "Ultima stampa" nella funzione di aggiornamento del documento PDF con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come configurare l'opzione per aggiornare la proprietà "Ultima stampa" durante la conversione in PDF.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio, supponiamo che il documento si chiami "Rendering.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: configurare le opzioni Salva come PDF con la proprietà "Ultima stampa" aggiornata

 Per abilitare l'aggiornamento della proprietà "Ultima stampa" durante la conversione in PDF, è necessario configurare il file`PdfSaveOptions` oggetto e impostare il`UpdateLastPrintedProperty` proprietà a`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Passaggio 4: salva il documento come PDF con l'aggiornamento della proprietà "Ultima stampa".

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

È tutto ! Hai abilitato correttamente l'aggiornamento della proprietà "Ultima stampa" durante la conversione di un documento in PDF utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per l'aggiornamento della proprietà "Ultima stampa" con Aspose.Words per .NET


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Conclusione

In questo tutorial, abbiamo spiegato come aggiornare la proprietà "Last Printed" in un documento PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi indicati, puoi facilmente configurare l'opzione per aggiornare la proprietà "Ultima stampa" durante la conversione di un documento in PDF. Utilizzare questa funzione per tenere traccia dell'utilizzo dei documenti e delle informazioni correlate.

### Domande frequenti

#### D: Cos'è la proprietà "Ultima stampa" in un documento PDF?
R: La proprietà "Ultima stampa" in un documento PDF si riferisce alla data e all'ora dell'ultima stampa del documento. Questa proprietà può essere utile per tenere traccia delle informazioni sull'utilizzo e la gestione dei documenti.

#### D: Come posso aggiornare la proprietà "Ultima stampa" in un documento PDF con Aspose.Words per .NET?
R: Per aggiornare la proprietà "Ultima stampa" in un documento PDF con Aspose.Words per .NET, attenersi alla seguente procedura:

 Crea un'istanza di`Document` class che specifica il percorso del documento Word.

 Crea un'istanza di`PdfSaveOptions` classe e impostare il`UpdateLastPrintedProperty` proprietà a`true` per abilitare l'aggiornamento della proprietà "Ultimo stampato".

 Usa il`Save` metodo del`Document`class per salvare il documento in formato PDF specificando le opzioni di salvataggio.

#### D: Come posso verificare se la proprietà "Ultima stampa" è stata aggiornata nel documento PDF generato?
R: È possibile verificare se la proprietà "Ultima stampa" è stata aggiornata nel documento PDF generato aprendo il file PDF con un visualizzatore PDF compatibile, come Adobe Acrobat Reader, e visualizzando le informazioni sul documento. La data e l'ora dell'ultima stampa devono corrispondere alla data e all'ora della generazione del documento PDF.
