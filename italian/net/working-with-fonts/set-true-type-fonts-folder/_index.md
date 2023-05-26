---
title: Imposta la cartella dei font True Type
linktitle: Imposta la cartella dei font True Type
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata all'impostazione della cartella dei font true type durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-true-type-fonts-folder/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per impostare la cartella dei font true type durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare una cartella personalizzata contenente i caratteri True Type da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui vuoi salvare il documento renderizzato modificato. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: carica il documento da renderizzare
 Successivamente, è necessario caricare il documento di cui eseguire il rendering utilizzando il file`Document` classe. Assicurati di specificare il percorso del documento corretto.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: impostare la cartella dei caratteri True Type
 Ora puoi specificare la cartella dei font true type da utilizzare durante il rendering creando un'istanza del file`FontSettings` classe e utilizzando il`SetFontsFolder()` metodo per impostare la cartella dei caratteri. È possibile specificare una cartella personalizzata contenente i font True Type. Il secondo parametro a`SetFontsFolder()` indica se si desidera cercare anche nelle sottocartelle della cartella specificata.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Passaggio 4: salvare il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file usando l'estensione`Save()` metodo del`Document` classe. Assicurarsi di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Esempio di codice sorgente per la cartella Set True Type Fonts utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Tieni presente che questa impostazione sovrascriverà qualsiasi origine di font predefinita che viene cercata per impostazione predefinita. Ora verranno cercate solo queste cartelle
	// Caratteri durante il rendering o l'incorporamento di caratteri. Per aggiungere una fonte di carattere aggiuntiva mantenendo le fonti di carattere di sistema, utilizzare sia FontSettings.GetFontSources che
	// FontSettings.SetFontSources invece
	fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
	// Imposta le impostazioni dei caratteri
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare la cartella dei font true type durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente specificare una cartella personalizzata contenente i font True Type da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per lavorare con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare i caratteri utilizzati durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.