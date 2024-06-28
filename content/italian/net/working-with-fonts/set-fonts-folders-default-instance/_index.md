---
title: Imposta l'istanza predefinita delle cartelle dei caratteri
linktitle: Imposta l'istanza predefinita delle cartelle dei caratteri
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare la cartella dei caratteri predefinita durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-default-instance/
---

In questo tutorial, ti guideremo attraverso il processo passo passo per impostare la cartella dei caratteri predefinita durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come impostare la cartella dei caratteri predefinita da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento renderizzato modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: imposta la cartella dei caratteri predefinita
 Quindi puoi impostare la cartella dei caratteri predefinita utilizzando il file`FontSettings.DefaultInstance` classe e il`SetFontsFolder()`metodo. Specifica il percorso della cartella dei caratteri che desideri utilizzare come cartella predefinita.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Passaggio 3: caricare il documento da renderizzare
 Ora puoi caricare il documento da renderizzare utilizzando il file`Document` classe. Assicurati di specificare il percorso corretto del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 4: salva il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file utilizzando il file`Save()` metodo del`Document` classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Codice sorgente di esempio per l'istanza predefinita delle cartelle di caratteri impostati utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare la cartella dei caratteri predefinita durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi facilmente specificare quale cartella di caratteri utilizzare come cartella predefinita durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per l'elaborazione delle parole con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso impostare le cartelle dei caratteri predefinite in Aspose.Words?

 R: Per impostare le cartelle dei caratteri predefinite in Aspose.Words, è necessario utilizzare il file`Fonts` classe e il`SetFontsFolders` metodo per specificare le posizioni delle cartelle dei caratteri personalizzati.

#### D: L'impostazione delle cartelle dei caratteri predefinite influisce su tutti i documenti Word elaborati con Aspose.Words?

R: Sì, l'impostazione delle cartelle di caratteri predefinite influisce su tutti i documenti Word elaborati con Aspose.Words. Dopo aver impostato le cartelle dei caratteri predefinite, Aspose.Words utilizzerà queste posizioni per cercare i caratteri in tutti i documenti.

#### D: Posso impostare più cartelle di caratteri predefinite in Aspose.Words?

 R: Sì, puoi impostare più cartelle di caratteri predefinite in Aspose.Words. Devi solo specificare le posizioni delle cartelle di caratteri personalizzati utilizzando il file`SetFontsFolders` metodo del`Fonts` classe.

#### D: Come posso controllare le cartelle dei caratteri predefinite attualmente impostate in Aspose.Words?

 R: Per controllare le cartelle di caratteri predefinite attualmente definite in Aspose.Words, puoi utilizzare il file`GetFolders` metodo del`Fonts` class per ottenere le posizioni delle cartelle dei caratteri configurate.

#### D: L'impostazione di cartelle di caratteri predefinite mi consente di utilizzare caratteri personalizzati nei miei documenti Word?

R: Sì, impostando cartelle di caratteri predefinite, puoi utilizzare caratteri personalizzati nei tuoi documenti Word. Devi solo posizionare i caratteri nelle cartelle specificate e Aspose.Words li utilizzerà durante la generazione o la manipolazione dei documenti.