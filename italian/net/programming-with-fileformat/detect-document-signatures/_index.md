---
title: Rileva le firme dei documenti
linktitle: Rileva le firme dei documenti
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo-passo per rilevare le firme digitali in un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-fileformat/detect-document-signatures/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzione di rilevamento della firma del documento con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come rilevare le firme digitali in un documento.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: rileva le firme digitali

 Successivamente, usiamo il`DetectFileFormat` metodo del`FileFormatUtil` class per rilevare le informazioni sul formato del file. In questo esempio, supponiamo che il documento si chiami "Digitally signed.docx" e si trovi nella directory dei documenti specificata.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Passaggio 3: verificare la presenza di firme digitali

 Controlliamo se il documento contiene firme digitali utilizzando il`HasDigitalSignature` proprietà del`FileFormatInfo` oggetto. Se vengono rilevate firme digitali, viene visualizzato un messaggio che indica che le firme andranno perse se il documento viene aperto/salvato con Aspose.Words.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

È tutto ! Hai rilevato correttamente le firme digitali in un documento utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per rilevare le firme dei documenti con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
