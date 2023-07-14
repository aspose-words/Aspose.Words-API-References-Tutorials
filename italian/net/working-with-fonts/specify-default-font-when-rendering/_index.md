---
title: Specifica carattere predefinito durante il rendering
linktitle: Specifica carattere predefinito durante il rendering
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per specificare il carattere predefinito durante il rendering di un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/specify-default-font-when-rendering/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per specificare il carattere predefinito durante il rendering di un documento utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come specificare un carattere predefinito da utilizzare durante il rendering dei tuoi documenti utilizzando Aspose.Words per .NET.

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

## Passaggio 3: imposta il carattere predefinito
 Ora puoi specificare il carattere predefinito da utilizzare durante il rendering creando un'istanza del file`FontSettings` classe e l'impostazione del`DefaultFontName`proprietà del`DefaultFontSubstitution` opporsi al`DefaultFontSubstitution` oggetto`SubstitutionSettings` Di`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Passaggio 4: salvare il documento renderizzato
 Infine, puoi salvare il documento renderizzato in un file usando l'estensione`Save()` metodo del`Document` classe. Assicurarsi di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Esempio di codice sorgente per specificare il carattere predefinito durante il rendering utilizzando Aspose.Words per .NET 

```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Se il carattere predefinito definito qui non può essere trovato durante il rendering, allora
// viene invece utilizzato il carattere più vicino sulla macchina.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come specificare il carattere predefinito durante il rendering di un documento utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente impostare un carattere predefinito da utilizzare durante il rendering dei tuoi documenti. Aspose.Words offre un'API potente e flessibile per l'elaborazione di testi con caratteri nei tuoi documenti. Con questa conoscenza, puoi controllare e personalizzare il rendering dei tuoi documenti in base alle tue esigenze specifiche.

### FAQ

#### D: Come posso specificare un carattere predefinito durante la conversione in PDF in Aspose.Words?

 R: Per specificare un carattere predefinito durante la conversione in PDF in Aspose.Words, puoi utilizzare il file`PdfOptions`classe e impostare il`DefaultFontName` property al nome del carattere desiderato.

#### D: Cosa succede se il carattere predefinito non è disponibile durante la conversione in PDF?

R: Se il carattere predefinito specificato non è disponibile durante la conversione in PDF, Aspose.Words utilizzerà un carattere sostitutivo per visualizzare il testo nel documento convertito. Ciò potrebbe causare una leggera differenza nell'aspetto rispetto al carattere originale.

#### D: Posso specificare un font predefinito per altri formati di output, come DOCX o HTML?

R: Sì, puoi specificare un carattere predefinito per altri formati di output come DOCX o HTML utilizzando le opzioni di conversione appropriate e impostando la proprietà corrispondente per ogni formato.

#### D: Come posso controllare il carattere predefinito specificato in Aspose.Words?

 R: Per verificare il carattere predefinito specificato in Aspose.Words, puoi utilizzare il file`DefaultFontName`proprietà del`PdfOptions` class e recuperare il nome del carattere configurato.

#### D: È possibile specificare un font predefinito diverso per ogni sezione del documento?

R: Sì, è possibile specificare un carattere predefinito diverso per ciascuna sezione del documento utilizzando le opzioni di formattazione specifiche per ciascuna sezione. Tuttavia, ciò richiederebbe una manipolazione più avanzata del documento utilizzando le funzionalità di Aspose.Words.