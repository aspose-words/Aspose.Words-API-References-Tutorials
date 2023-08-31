---
title: Imposta la cartella dei caratteri
linktitle: Imposta la cartella dei caratteri
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare la directory dei caratteri in Aspose.Words per .NET e garantire la disponibilità dei caratteri utilizzati nei tuoi documenti.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folder/
---
In questo tutorial, ti mostreremo come impostare la directory dei caratteri in Aspose.Words per .NET. Imparerai come specificare la directory contenente i caratteri utilizzati nel tuo documento Word.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Una conoscenza pratica del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: definire la directory dei documenti
 Inizia impostando il percorso della directory sulla posizione del tuo documento Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: imposta la directory dei caratteri
 Crea un'istanza di`FontSettings` classe e utilizzare il file`SetFontsFolder` metodo per specificare la directory contenente i caratteri. Sostituire`"Fonts"` con il nome della directory dei caratteri effettiva.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Passaggio 3: carica il documento con le impostazioni dei caratteri
 Usa il`LoadOptions` classe per specificare le impostazioni dei caratteri nel file`FontSettings` opzione. Quindi utilizzare il`Document` class per caricare il documento utilizzando queste opzioni.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Codice sorgente di esempio per la cartella Imposta caratteri utilizzando Aspose.Words per .NET 

```csharp

//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusione
Congratulazioni! Ora sai come impostare la directory dei caratteri in Aspose.Words per .NET. È possibile utilizzare questa funzionalità per garantire la disponibilità dei caratteri utilizzati nel documento e per garantire la coerenza nella visualizzazione dei caratteri.

### Domande frequenti

#### D: Come posso impostare una cartella di caratteri personalizzata in Aspose.Words?

 R: Per impostare una cartella di caratteri personalizzati in Aspose.Words, puoi utilizzare il file`FontsFolder` classe e il`SetFontsFolders` metodo che specifica il percorso della cartella contenente i caratteri.

#### D: Posso impostare più cartelle di caratteri in Aspose.Words?

 R: Sì, puoi impostare più cartelle di caratteri in Aspose.Words chiamando il file`SetFontsFolders` più volte con i percorsi delle diverse cartelle di caratteri che desideri utilizzare.

#### D: Cosa succede se un font utilizzato nel documento non è presente nelle cartelle dei font definite?

R: Se un carattere utilizzato nel documento non è presente nelle cartelle dei caratteri definite in Aspose.Words, verrà utilizzato invece un carattere sostitutivo. Ciò garantisce che il testo nel documento venga sempre visualizzato correttamente, anche se il carattere originale non è disponibile.

#### D: Le cartelle dei caratteri definite in Aspose.Words hanno la priorità sui caratteri installati nel sistema?

R: Sì, le cartelle dei caratteri definite in Aspose.Words hanno la precedenza sui caratteri installati nel sistema. Ciò significa che se sia nelle cartelle dei font definite che nei font di sistema è presente un font con lo stesso nome, durante l'elaborazione dei documenti Word verrà utilizzata la versione presente nella cartella dei font.