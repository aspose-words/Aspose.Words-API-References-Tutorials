---
title: Imposta le cartelle dei caratteri con priorità
linktitle: Imposta le cartelle dei caratteri con priorità
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata all'impostazione delle cartelle dei caratteri con priorità durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-with-priority/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per impostare le cartelle dei caratteri con priorità durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare più cartelle di font con priorità di ricerca personalizzata durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui vuoi salvare il documento renderizzato modificato. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: imposta le cartelle dei caratteri con priorità
 Quindi puoi impostare le cartelle dei caratteri con priorità utilizzando il file`FontSettings` classe e il`SetFontsSources()` metodo. È possibile specificare più fonti di font utilizzando le istanze di`SystemFontSource` E`FolderFontSource`. In questo esempio, abbiamo definito due sorgenti di font: la sorgente di font di sistema predefinita e una cartella di font personalizzata con priorità 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
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
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Esempio di codice sorgente per Imposta cartelle di caratteri con priorità utilizzando Aspose.Words per .NET 
```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare le cartelle dei caratteri con priorità durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente specificare più cartelle di font con priorità di ricerca personalizzata durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per lavorare con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.