---
title: Docx in formato Rtf
linktitle: Docx in formato Rtf
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire documenti Word da Docx in formato RTF utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/basic-conversions/docx-to-rtf/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un documento Word in formato Docx in RTF. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: lettura del documento da Stream

Innanzitutto, apri uno stream per leggere il documento Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Passaggio 2: caricamento del documento

Successivamente, carica il documento dallo stream:

```csharp
Document doc = new Document(stream);
```

## Passaggio 3: chiusura dello stream

Poiché il documento è caricato in memoria, puoi chiudere lo stream:

```csharp
stream.Close();
```

## Passaggio 4: eseguire operazioni sul documento

A questo punto è possibile eseguire qualsiasi operazione desiderata sul documento.

## Passaggio 5: salvare il documento in formato RTF

Per salvare il documento in formato RTF, salvalo in un flusso di memoria:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Passaggio 6: riavvolgimento del flusso

Prima di scrivere il flusso di memoria su un file, riavvolgi la sua posizione a zero:

```csharp
dstStream.Position = 0;
```

## Passaggio 7: scrittura del flusso su file

Infine, scrivi il flusso di memoria in un file RTF:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

Questo è tutto! Hai convertito con successo un documento Word in formato Docx in RTF utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Docx To Rtf utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// L'accesso in sola lettura è sufficiente per Aspose.Words per caricare un documento.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//Puoi chiudere lo stream ora, non è più necessario perché il documento è in memoria.
	stream.Close();

	// ... fare qualcosa con il documento.

	// Converti il documento in un formato diverso e salvalo in streaming.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Riavvolgi la posizione dello stream su zero in modo che sia pronta per il prossimo lettore.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.