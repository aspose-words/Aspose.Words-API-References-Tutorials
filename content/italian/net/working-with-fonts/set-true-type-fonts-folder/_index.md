---
title: Imposta la cartella dei caratteri True Type
linktitle: Imposta la cartella dei caratteri True Type
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare la cartella dei caratteri true type durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-true-type-fonts-folder/
---

In questo tutorial, ti guideremo attraverso il processo passo passo per impostare la cartella dei caratteri true type durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare una cartella personalizzata contenente i caratteri True Type da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento renderizzato modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento da renderizzare
 Successivamente, è necessario caricare il documento da renderizzare utilizzando il file`Document` classe. Assicurati di specificare il percorso corretto del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: imposta la cartella dei caratteri True Type
Ora puoi specificare la cartella dei caratteri true type da utilizzare durante il rendering creando un'istanza del file`FontSettings` classe e utilizzando il file`SetFontsFolder()` metodo per impostare la cartella dei caratteri. Puoi specificare una cartella personalizzata contenente i tuoi font True Type. Il secondo parametro a`SetFontsFolder()` indica se si desidera eseguire la ricerca anche nelle sottocartelle della cartella specificata.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Passaggio 4: salva il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file utilizzando il file`Save()` metodo del`Document` classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Codice sorgente di esempio per la cartella Imposta caratteri True Type utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Tieni presente che questa impostazione sovrascriverà qualsiasi origine di caratteri predefinita ricercata per impostazione predefinita. Ora verranno cercate solo queste cartelle
// Caratteri durante il rendering o l'incorporamento di caratteri. Per aggiungere un'origine di caratteri aggiuntiva mantenendo le origini di caratteri di sistema, utilizzare sia FontSettings.GetFontSources che
// FontSettings.SetFontSources invece
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Configura le impostazioni dei caratteri
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare la cartella dei caratteri di tipo reale durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi facilmente specificare una cartella personalizzata contenente i caratteri True Type da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per l'elaborazione delle parole con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare i caratteri utilizzati durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso configurare la cartella dei caratteri TrueType in Aspose.Words?

 R: Per configurare la cartella dei caratteri TrueType in Aspose.Words, è possibile utilizzare il file`SetTrueTypeFontsFolder` metodo del`Fonts` classe che specifica la posizione della cartella contenente i caratteri TrueType.

#### D: Quali tipi di caratteri sono considerati caratteri TrueType?

R: I caratteri TrueType sono un formato di carattere molto diffuso. Sono spesso utilizzati nei documenti di Word e hanno un'estensione di file .ttf o .ttc.

#### D: Posso specificare più cartelle di caratteri TrueType in Aspose.Words?

R: Sì, puoi specificare più cartelle di caratteri TrueType in Aspose.Words utilizzando il file`SetTrueTypeFontsFolder` metodo del`Fonts` classe con un elenco di posizioni delle cartelle.

#### D: Come posso controllare la cartella dei caratteri TrueType configurata in Aspose.Words?

 R: Per controllare la cartella TrueType Fonts configurata in Aspose.Words, puoi utilizzare il file`GetTrueTypeFontsFolder` metodo del`Fonts` class per ottenere il percorso della cartella TrueType Fonts configurata.

#### D: Perché è importante configurare la cartella dei caratteri TrueType in Aspose.Words?

R: L'impostazione della cartella dei caratteri TrueType in Aspose.Words è importante perché aiuta Aspose.Words a individuare i caratteri necessari durante l'elaborazione dei documenti di Word. Ciò garantisce coerenza nella formattazione e nell'aspetto dei documenti, anche tra sistemi diversi.