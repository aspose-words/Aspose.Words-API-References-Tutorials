---
title: Rileva il formato del file del documento
linktitle: Rileva il formato del file del documento
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo passo per rilevare il formato del file del documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-fileformat/detect-file-format/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzione di rilevamento del formato del file del documento con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come rilevare il formato di diversi file di documenti.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire le directory

 Per iniziare, è necessario definire le directory in cui si desidera archiviare i file in base al loro formato. Sostituire`"YOUR DOCUMENT DIRECTORY"`con il percorso effettivo della directory dei documenti. Creiamo le directory "Supported", "Unknown", "Encrypted" e "Pre97" se non esistono già.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Crea le directory se non esistono già.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Passaggio 2: sfoglia i file

 Quindi usiamo il`GetFiles` metodo del`Directory` class per ottenere l'elenco dei file nella directory specificata. Usiamo anche a`Where` clausola per escludere un file specifico denominato "Corrupted document.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Passo 3: Rileva il formato di ciascun file

 Esaminiamo ogni file nell'elenco e usiamo l'estensione`DetectFileFormat` metodo del`FileFormatUtil` class per rilevare il formato del file. Visualizziamo anche il tipo di documento rilevato.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Visualizza il tipo di documento
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Aggiungi casi per altri formati di documenti supportati
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

È tutto ! Hai rilevato con successo il formato di diversi file di documento utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per il rilevamento del formato file con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Creare le directory se non esistono già.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Visualizza il tipo di documento
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### Domande frequenti per il rilevamento del formato di file del documento

#### Come rilevare il formato di un file di documento utilizzando Aspose.Words per .NET?

 Per rilevare il formato di un file di documento utilizzando Aspose.Words per .NET, è possibile seguire i passaggi forniti nel tutorial. Usando il`DetectFileFormat` metodo del`FileFormatUtil` class ti permetterà di rilevare il formato del file del documento. Ciò consentirà di determinare se si tratta di un documento Microsoft Word 97-2003, un modello, un documento Office Open XML WordprocessingML o altri formati supportati. Il codice fornito nel tutorial ti guiderà attraverso l'implementazione di questa funzione.

#### Quali formati di documento supporta Aspose.Words per .NET?

Aspose.Words per .NET supporta una varietà di formati di documenti inclusi documenti Microsoft Word 97-2003 (DOC), modelli (DOT), documenti Office Open XML WordprocessingML (DOCX), documenti Office Open XML WordprocessingML con macro (DOCM), Office Open Modelli XML WordprocessingML senza macro (DOTX), modelli Office Open XML WordprocessingML con macro (DOTM), documenti Flat OPC, documenti RTF, documenti Microsoft Word 2003 WordprocessingML, documenti HTML, documenti MHTML (archivio Web), documenti OpenDocument Text (ODT), Modelli OpenDocument Text (OTT), documenti MS Word 6 o Word 95 e formati di documenti sconosciuti.

#### Come gestire i file di documenti crittografati durante il rilevamento del formato?

 Quando si rileva il formato di un file di documento, è possibile utilizzare l'estensione`IsEncrypted` proprietà del`FileFormatInfo` oggetto per verificare se il file è crittografato. Se il file è crittografato, puoi eseguire ulteriori passaggi per gestire questo caso specifico, come copiare il file in una directory dedicata ai documenti crittografati. Puoi usare il`File.Copy` metodo per farlo.

#### Quali azioni dovrebbero essere intraprese quando il formato di un documento è sconosciuto?

Quando il formato di un documento è sconosciuto, puoi decidere di gestirlo in modo specifico per la tua applicazione. Nell'esempio fornito nel tutorial, il documento viene copiato in una directory specifica dedicata ai documenti di formato sconosciuto. È possibile personalizzare questa azione in base alle proprie esigenze specifiche.

#### Esistono altre funzionalità di Aspose.Words per .NET che possono essere utilizzate insieme al rilevamento del formato del documento?

Sì, Aspose.Words per .NET offre molte altre funzionalità per l'elaborazione e la manipolazione di documenti Word. Ad esempio, puoi utilizzare la libreria per estrarre testo, immagini o metadati dai documenti, applicare modifiche alla formattazione, unire documenti, convertire documenti in formati diversi e altro ancora.