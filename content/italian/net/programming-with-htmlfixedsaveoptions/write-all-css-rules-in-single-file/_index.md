---
title: Scrivi tutte le regole CSS in un unico file
linktitle: Scrivi tutte le regole CSS in un unico file
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come convertire un documento Word in HTML fisso scrivendo tutte le regole CSS in un unico file con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Quando converti un documento Word in HTML fisso in un'applicazione C#, potresti voler consolidare tutte le regole CSS in un unico file per una migliore organizzazione e portabilità. Con la libreria Aspose.Words per .NET, puoi facilmente specificare questa funzionalità utilizzando le opzioni di salvataggio HtmlFixedSaveOptions. In questa guida passo passo, ti spiegheremo come utilizzare Aspose.Words per il codice sorgente .NET C# per convertire un documento Word in HTML fisso scrivendo tutte le regole CSS in un singolo file utilizzando le opzioni di salvataggio HtmlFixedSaveOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme tra cui .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Caricamento del documento Word

Il primo passo è caricare il documento Word che desideri convertire in HTML fisso. Utilizzare la classe Document per caricare il documento dal file sorgente. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In questo esempio carichiamo il documento "Document.docx" che si trova nella directory dei documenti.

## Configurazione delle opzioni di backup

Il passaggio successivo consiste nel configurare le opzioni di salvataggio per la conversione in HTML fisso. Utilizza la classe HtmlFixedSaveOptions e imposta la proprietà SaveFontFaceCssSeparately su false per scrivere tutte le regole CSS in un singolo file. Ecco come farlo:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Creiamo un nuovo oggetto HtmlFixedSaveOptions e impostiamo la proprietà SaveFontFaceCssSeparately su false per scrivere tutte le regole CSS in un unico file.

## Corretta la conversione del documento HTML

Ora che abbiamo configurato le opzioni di salvataggio, possiamo procedere con la conversione del documento in HTML fisso. Utilizza il metodo Save della classe Document per salvare il documento convertito in formato HTML fisso specificando le opzioni di salvataggio. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

In questo esempio, salviamo il documento convertito come "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" utilizzando le opzioni di salvataggio specificate.

### Esempio di codice sorgente per HtmlFixedSaveOptions con la funzionalità "Scrivi tutte le regole CSS in un file" utilizzando Aspose.Words per .NET

```csharp
// Percorso di accesso alla directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento di Word
Document doc = new Document(dataDir + "Document.docx");

// Configura le opzioni di backup con la funzione "Scrivi tutte le regole CSS in un file".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Converti il documento in HTML fisso
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come convertire un documento Word in HTML fisso scrivendo tutte le regole CSS in un singolo file utilizzando HtmlFixedSaveOptions con la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e utilizzando il codice sorgente C# fornito, puoi applicare facilmente questa funzionalità nella tua applicazione C#. Scrivere tutte le regole CSS in un unico file semplifica l'organizzazione e la gestione del codice HTML generato durante la conversione del documento.