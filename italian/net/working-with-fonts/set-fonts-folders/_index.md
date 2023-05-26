---
title: Imposta le cartelle dei caratteri
linktitle: Imposta le cartelle dei caratteri
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata all'impostazione delle cartelle dei caratteri durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per impostare le cartelle dei caratteri durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare le cartelle dei font da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui vuoi salvare il documento renderizzato modificato. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: imposta le origini dei caratteri
 Quindi puoi impostare le fonti dei caratteri usando il file`FontSettings.DefaultInstance` classe e il`SetFontsSources()` metodo. In questo esempio, utilizziamo sia un'origine di font di sistema che un'origine di font di cartelle personalizzate. Assicurati di regolare il percorso della cartella dei caratteri personalizzati in base alle tue esigenze.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Passo 3: Carica il documento da renderizzare
 Ora puoi caricare il documento di cui eseguire il rendering utilizzando il file`Document` classe. Assicurati di specificare il percorso del documento corretto.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 4: salvare il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file usando l'estensione`Save()` metodo del`Document` classe. Assicurarsi di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Codice sorgente di esempio per impostare le cartelle dei caratteri utilizzando Aspose.Words per .NET 
```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare le cartelle dei caratteri durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente specificare le origini dei caratteri da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per lavorare con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.