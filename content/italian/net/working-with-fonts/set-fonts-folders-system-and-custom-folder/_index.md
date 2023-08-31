---
title: Imposta il sistema di cartelle dei caratteri e la cartella personalizzata
linktitle: Imposta il sistema di cartelle dei caratteri e la cartella personalizzata
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare cartelle di caratteri di sistema e personalizzate durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

In questo tutorial, ti guideremo attraverso il processo passo passo per impostare le cartelle dei caratteri di sistema e una cartella personalizzata durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare più cartelle di caratteri, inclusa la cartella di sistema e una cartella personalizzata, da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento renderizzato modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento da renderizzare
 Quindi puoi caricare il documento da renderizzare utilizzando il file`Document` classe. Assicurati di specificare il percorso corretto del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: imposta le cartelle dei caratteri di sistema e personalizzati
 Ora puoi impostare le cartelle dei caratteri di sistema e una cartella personalizzata utilizzando il file`FontSettings` classe e il`SetFontsSources()` metodo. Innanzitutto, è necessario recuperare l'elenco delle origini dei caratteri dipendenti dall'ambiente utilizzando`GetFontsSources()` e memorizzarlo in un elenco. Quindi puoi creare una nuova istanza di`FolderFontSource` specificando il percorso della cartella personalizzata contenente i tuoi caratteri. Aggiungi questa istanza all'elenco delle origini dei caratteri esistenti. Infine, usa`SetFontsSources()` per aggiornare le origini dei caratteri con il nuovo elenco.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Passaggio 4: applica le impostazioni dei caratteri
 Successivamente, devi applicare le impostazioni del carattere al tuo documento utilizzando il file`FontSettings` proprietà del`Document` classe.

```csharp
doc.FontSettings = fontSettings;
```

## Passaggio 5: salva il documento renderizzato
Infine, puoi salvare il documento renderizzato in un file con

   usando il`Save()` metodo del`Document` classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Codice sorgente di esempio per il sistema di cartelle Set Fonts e la cartella personalizzata utilizzando Aspose.Words per .NET 

```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Recupera la serie di origini di caratteri dipendenti dall'ambiente ricercate per impostazione predefinita.
// Ad esempio, questo conterrà un'origine "Windows\Fonts\" su macchine Windows.
// Aggiungiamo questo array a un nuovo elenco per rendere molto più semplice l'aggiunta o la rimozione di voci di caratteri.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Aggiungi una nuova sorgente di cartella che indicherà ad Aspose.Words di cercare i caratteri nella seguente cartella.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Aggiungi la cartella personalizzata che contiene i nostri caratteri all'elenco delle fonti di caratteri esistenti.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare le cartelle dei caratteri di sistema e una cartella personalizzata durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi facilmente specificare più cartelle di caratteri, inclusa la cartella di sistema e una cartella personalizzata, da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per l'elaborazione delle parole con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso impostare le cartelle dei caratteri di sistema in Aspose.Words?

R: Per impostare le cartelle dei caratteri di sistema in Aspose.Words, non devi fare nulla. Aspose.Words utilizza automaticamente i caratteri di sistema installati sul sistema operativo.

#### D: Come posso impostare cartelle di caratteri personalizzate in Aspose.Words?

 R: Per impostare le cartelle di caratteri personalizzati in Aspose.Words, puoi utilizzare il file`SetFontsFolders` metodo del`Fonts` classe che specifica le posizioni delle cartelle dei caratteri personalizzati.

#### D: Posso specificare più cartelle di caratteri personalizzati in Aspose.Words?

 R: Sì, puoi specificare più cartelle di caratteri personalizzati in Aspose.Words utilizzando il file`SetFontsFolders` metodo del`Fonts` classe con un elenco di posizioni delle cartelle.

#### D: Come posso controllare le cartelle dei caratteri definite in Aspose.Words?

 Per controllare le cartelle dei caratteri definite in Aspose.Words, puoi utilizzare il file`GetFolders` metodo del`Fonts` class per ottenere l'elenco delle cartelle di caratteri configurate.

#### D: I caratteri delle cartelle personalizzate hanno la priorità sui caratteri di sistema in Aspose.Words?

R: Sì, i caratteri delle cartelle personalizzate hanno la priorità sui caratteri di sistema in Aspose.Words. Se un carattere è presente sia nelle cartelle personalizzate che nei caratteri di sistema, Aspose.Words utilizzerà la versione dalla cartella personalizzata.