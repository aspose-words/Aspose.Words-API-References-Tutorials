---
title: Imposta le cartelle dei caratteri con priorità
linktitle: Imposta le cartelle dei caratteri con priorità
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare le cartelle dei caratteri con priorità durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-with-priority/
---

In questo tutorial, ti guideremo attraverso il processo passo passo per impostare le cartelle dei caratteri con priorità durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare più cartelle di caratteri con priorità di ricerca personalizzata durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento renderizzato modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: imposta la priorità sulle cartelle dei caratteri
 Quindi puoi impostare le cartelle dei caratteri con priorità utilizzando il file`FontSettings` classe e il`SetFontsSources()`metodo. È possibile specificare più origini di caratteri utilizzando istanze di`SystemFontSource` E`FolderFontSource`. In questo esempio, abbiamo definito due origini di caratteri: l'origine di caratteri di sistema predefinita e una cartella di caratteri personalizzata con priorità 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Passaggio 3: caricare il documento da renderizzare
 Ora puoi caricare il documento da renderizzare utilizzando il file`Document` classe. Assicurati di specificare il percorso corretto del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 4: salva il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file utilizzando il file`Save()` metodo del`Document` classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Codice sorgente di esempio per Imposta cartelle di caratteri con priorità utilizzando Aspose.Words per .NET 
```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare le cartelle dei caratteri con priorità durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi facilmente specificare più cartelle di caratteri con priorità di ricerca personalizzata durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per l'elaborazione delle parole con i caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare le origini dei caratteri utilizzate durante il rendering dei tuoi documenti in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso impostare le cartelle dei caratteri con priorità in Aspose.Words?

 R: Per impostare le cartelle dei caratteri con priorità in Aspose.Words, puoi utilizzare il file`SetFontsFoldersWithPriority` metodo del`Fonts` classe specificando le posizioni delle cartelle dei caratteri e il loro ordine di priorità.

#### D: Cosa succede se un font è presente in più cartelle con priorità diversa?

R: Se un carattere è presente in più cartelle con priorità diversa, Aspose.Words utilizzerà la versione della cartella con la priorità più alta durante l'elaborazione dei documenti.

#### D: Posso specificare più cartelle di caratteri con la stessa priorità in Aspose.Words?

R: Sì, puoi specificare più cartelle di caratteri con la stessa priorità in Aspose.Words. Aspose.Words li considererà tutti con la stessa priorità durante la ricerca dei caratteri nei tuoi documenti.

#### D: Come posso controllare le cartelle dei caratteri definite con priorità in Aspose.Words?

 R: Per controllare le cartelle dei caratteri definite con priorità in Aspose.Words, puoi utilizzare il file`GetFolders` metodo del`Fonts` class per ottenere l'elenco delle cartelle di caratteri configurate incluso il loro ordine di priorità.

#### D: A che serve impostare le cartelle dei caratteri con priorità in Aspose.Words?

R: L'impostazione delle cartelle dei caratteri con priorità in Aspose.Words consente di controllare l'ordine di ricerca dei caratteri nei documenti di Word. Ciò ti aiuta a garantire che vengano utilizzati i caratteri desiderati ed evitare problemi di sostituzione dei caratteri indesiderati.