---
title: Imposta la cartella dei caratteri
linktitle: Imposta la cartella dei caratteri
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come impostare la directory dei caratteri in Aspose.Words per .NET e garantire la disponibilità dei caratteri utilizzati nei tuoi documenti.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folder/
---
In questo tutorial, ti mostreremo come impostare la directory dei caratteri in Aspose.Words per .NET. Imparerai come specificare la directory contenente i caratteri utilizzati nel tuo documento Word.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: definire la directory dei documenti
 Inizia impostando il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: imposta la directory dei caratteri
 Crea un'istanza di`FontSettings` classe e utilizzare il`SetFontsFolder` metodo per specificare la directory contenente i caratteri. Sostituire`"Fonts"` con il nome dell'effettiva directory dei font.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Passaggio 3: caricare il documento con le impostazioni dei caratteri
 Usa il`LoadOptions` class per specificare le impostazioni dei caratteri nel file`FontSettings` opzione. Quindi usa il`Document` class per caricare il documento usando queste opzioni.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Esempio di codice sorgente per la cartella Set Fonts utilizzando Aspose.Words per .NET 

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
Congratulazioni! Ora sai come impostare la directory dei caratteri in Aspose.Words per .NET. È possibile utilizzare questa funzione per garantire la disponibilità dei caratteri utilizzati nel documento e per garantire la coerenza nella visualizzazione dei caratteri.

### FAQ

#### D: Come posso impostare una cartella di font personalizzata in Aspose.Words?

 A: Per impostare una cartella di caratteri personalizzati in Aspose.Words, puoi utilizzare il`FontsFolder` classe e il`SetFontsFolders` metodo specificando il percorso della cartella contenente i font.

#### D: Posso impostare più cartelle di font in Aspose.Words?

 A: Sì, puoi impostare più cartelle di font in Aspose.Words chiamando il file`SetFontsFolders` metodo più volte con i percorsi delle diverse cartelle di font che si desidera utilizzare.

#### D: Cosa succede se un font utilizzato nel documento non è presente nelle cartelle dei font definite?

R: Se un font utilizzato nel documento non è presente nelle cartelle dei font definite in Aspose.Words, verrà utilizzato un font sostitutivo. Ciò garantisce che il testo nel documento venga sempre visualizzato correttamente, anche se il carattere originale non è disponibile.

#### D: Le cartelle dei font definite in Aspose.Words hanno la priorità sui font installati nel sistema?

R: Sì, le cartelle dei font definite in Aspose.Words hanno la precedenza sui font installati nel sistema. Ciò significa che se un font con lo stesso nome è presente sia nelle cartelle dei font definite sia nei font di sistema, durante l'elaborazione dei documenti Word verrà utilizzata la versione nella cartella dei font.