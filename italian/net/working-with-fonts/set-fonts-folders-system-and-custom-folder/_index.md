---
title: Imposta il sistema delle cartelle dei caratteri e la cartella personalizzata
linktitle: Imposta il sistema delle cartelle dei caratteri e la cartella personalizzata
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata all'impostazione delle cartelle di sistema e dei caratteri personalizzati durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per impostare le cartelle dei font di sistema e una cartella personalizzata durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare più cartelle di font, inclusa la cartella di sistema e una cartella personalizzata, da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui vuoi salvare il documento renderizzato modificato. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: carica il documento da renderizzare
 Quindi puoi caricare il documento di cui eseguire il rendering utilizzando il file`Document` classe. Assicurati di specificare il percorso del documento corretto.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: imposta le cartelle di sistema e dei caratteri personalizzati
 Ora puoi impostare le cartelle dei font di sistema e una cartella personalizzata utilizzando il file`FontSettings` classe e il`SetFontsSources()` metodo. Innanzitutto, è necessario recuperare l'elenco delle fonti di font dipendenti dall'ambiente utilizzando`GetFontsSources()` e memorizzarlo in un elenco. Quindi puoi creare una nuova istanza di`FolderFontSource`specificando il percorso della cartella personalizzata contenente i font. Aggiungi questa istanza all'elenco delle fonti di font esistenti. Infine, usa`SetFontsSources()` per aggiornare le fonti dei caratteri con il nuovo elenco.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Passaggio 4: applica le impostazioni dei caratteri
 Successivamente, è necessario applicare le impostazioni del carattere al documento utilizzando il file`FontSettings` proprietà del`Document` classe.

```csharp
doc.FontSettings = fontSettings;
```

## Passaggio 5: salvare il documento renderizzato
Infine, puoi salvare il documento renderizzato in un file tramite

   usando il`Save()` metodo del`Document` classe. Assicurarsi di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Esempio di codice sorgente per il sistema di cartelle di caratteri impostati e la cartella personalizzata utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Recupera l'array di fonti di font dipendenti dall'ambiente che vengono cercate per impostazione predefinita.
	// Ad esempio, questo conterrà un'origine "Windows\Fonts\" su un computer Windows.
	// Aggiungiamo questo array a un nuovo elenco per rendere molto più semplice l'aggiunta o la rimozione di voci di font.
	List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
	// Aggiungi una nuova cartella sorgente che istruirà Aspose.Words a cercare i caratteri nella seguente cartella.
	FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
	// Aggiungi la cartella personalizzata che contiene i nostri font all'elenco delle fonti di font esistenti.
	fontSources.Add(folderFontSource);
	FontSourceBase[] updatedFontSources = fontSources.ToArray();
	fontSettings.SetFontsSources(updatedFontSources);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare le cartelle dei font di sistema e una cartella personalizzata durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente specificare più cartelle di font, inclusa la cartella di sistema e una cartella personalizzata, da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per lavorare con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.